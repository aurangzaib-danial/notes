# Files validation
Uploading files using the direct_upload feature has edge cases.
1. We can only validate the file on the client side.
2. If the file is uploaded to the cloud storage but the record is not saved then we have orphaned files in our storage drive.

## Resolution
First of all, add validation on the client side and that should be more than enough for now. In your current state, you cant really validate these files. Also, storage is cheap so we do not really need to worry about running out of space in storage drive. 

Keep this issue in the back of your mind and keep making apps using ActiveStorage and ActionText. We will address this problem when we are really concerned about security.
