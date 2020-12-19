# Layouts
## Mobile first approach
- This approach is much more logical than desktop-first approach because it is based on progressive enhancement.
- Desktop-first layouts become complex quickly and it becomes really difficult to bring them down to a smaller level.
- Mobile-first approach starts from a one-column layout and then we can keep enhancing it according to our requirement, without over-complicating.

## Deciding on media queries
- Decide on a media query according to the resizing of the window and not by popular devices.
- It can be tempting to use a lot of media queries but we should use only what we require and try not be perfect.
- Try to use relative units like `ems` or `rems` for media queries because they will allow zooming capability of browsers to fire the right media query and avoid horizontal scroll bars while zooming in. 


[Thorough article on Mobile first approach](https://bradfrost.com/blog/post/mobile-first-responsive-web-design/)
[Article on media queries](https://bradfrost.com/blog/post/7-habits-of-highly-effective-media-queries/)
