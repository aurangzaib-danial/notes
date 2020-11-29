# Introduction
ActiveJob is a built-in Rails framework for handling jobs that need to be ran in the background.
Jobs are asynchronous, run in the background and keep the main application free from unecessary workload.

## Jobs vs Workers
Jobs are running in the background while workers are for handling multiple requests at a time.
So if I want to download something in the background I would use jobs.
And if I want to keep the main request/response cycle free when uploading files, I will delegate uploading to a worker.
