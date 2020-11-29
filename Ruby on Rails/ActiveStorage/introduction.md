# ActiveStorage
It is the Rails solution for solving the problem of files upload/download etc. It is fairly simple and has a very simple setup.

By default, files are stored in the root/storage folder of app. We can easily make tell ActiveStorage to use third clouds e.g. Google, Amazon etc.

**We can refer the rails guides as to how setup a third party cloud and also customizing the active_storage settings**.

## Reservations
1. Larger files will stuck my server.
2. Validation of files.

The solution to above problems is put validations for files like format, size etc but larger files will automatically timeout in production servers, we do not need to worry about that.

> How does the file travels from browser to server and how does the server downloads the file from client and then passes it controller for handling is extremely low level. We only need to worry about writing code and let others take care of these low level technologies.
 
## Setup
ActiveStorage stores all of the blobs(attachment data) in a single polmorphic table. Files are stored inside root/storage of app.

```console
// without generate command
$ rails active_storage:install
```
Above commands creates the migrations that we require of the polymorphic table.



