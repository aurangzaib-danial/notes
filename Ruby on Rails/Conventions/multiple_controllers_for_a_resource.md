# Multiple Controllers for a resources
To understand this convention, consider example of a Post model.

I would have PostsController in my controllers directory that controls all public requests related to Posts.

In terms of managing a Posts, I would have a Manage::PostsController that manages all administrative aspects of Posts.

This way public and manageable concerns are separated. If we were to do all of this in a single controller then our controller file will become huge and difficult to understand.

**Remember, we should only have 7 actions at most inside a controleller file**



