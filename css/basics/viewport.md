# Viewport
The area of the browser's window in which the web content can be seen.

## Importance of setting viewport for mobile devices
In past, not all websites were responsive. If the viewport was kept as same as the mobile device width then when a website which was not responsive and had fixed width, was loaded, the users would have horizontal scroll bars for viewing the website.

For this very reason, a by default viewport was established in browsers which is 980px, this way no matter what the size of website is, whole of the website will be visible in the viewport without horizontal scroll bar and users can zoom to look at specific parts of website.

Our CSS media queries depend on the viewport of the browser. If the viewport doesn't change then our media queries also do not trigger. To overwrite the browser's default value for viewport we use 'viewport meta tag' to set the viewport same as the device width. This way those who have responsive websites can easily scale their content and instead of complete web content on the viewport they can offer vertical scrolling to the users and also make the content large so the users do not have to zoom.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- width=device-width => sets the viewport width as the device width -->
<!-- initial-scale=1.0 => sets the zoom level to default -->
<!-- user-scalable=false => Disable zoom (avoid this) -->
```

> Users hate horizontal scrolling and a website without zoom feature. We need to avoid this at all cost.
