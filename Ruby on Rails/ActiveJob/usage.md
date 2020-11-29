# Usage
ActiveJob is very simple to use.
First of all generate an active_job file.

```bash
$ rails g job ImageDownload
#=> app/jobs/image_download_job.rb & test files
```

```ruby
# typical job file
class ImageDownloadJob < ApplicationJob
  queue: :default

  def perform(image_url)
    file = Down.download(image_url) #=> download the file in the background
  end
end

ImageDownloadJob.perform_later(image_url) #=> queue it up and do it later
.perform_now #=> do it now
```

**We can only pass persisted model objects to active job because otherwise it cannot keep track of the objects in the memory**
