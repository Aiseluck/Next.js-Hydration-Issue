# Next.js Framework Not Detecting Hydration Error for Rendered Button with Disabled Property"

## Introduction

When the button's disable property depends on a browser window object property, server-side rendering and client-side rendering may differ due to the window object's absence on the server side.

This should trigger a hydration error, but Next.js does not alert users to this issue, which can lead to unexpected behavior.

Please note that this problem will be encountered when attempting to render buttons with dependencies on browser window object properties

For instance if

```javascript
buttonProperty = window. // any Property evaluating to either true or false
```

```html
<button disabled="{buttonProperty}"></button>
```

NextJs should alert the user to this as there would be a difference in the Client and Server Side Rendering
