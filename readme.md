I understand your instructions clearly. I will write a comprehensive guide on building a Chrome extension, formatted as a textbook for a computer science student. The guide will include all necessary code and scripts with detailed comments for better understanding. I will cover the following components: manifest file, service workers, content-script, popup folder, options folder, and icons folder. I will also provide information on any required APIs and their endpoints.

Please provide the functionality of the Chrome extension you want me to describe, and I will create a detailed guide accordingly.

---

# Building a Chrome Extension: A Comprehensive Guide

This guide will walk you through the process of building a Chrome extension, focusing on a specific functionality. We will cover the following components:

1. [Manifest File](#manifest-file)
2. [Service Workers](#service-workers)
3. [Content Script](#content-script)
4. [Popup Folder](#popup-folder)
5. [Options Folder](#options-folder)
6. [Icons Folder](#icons-folder)
7. [Chrome Extensions APIs and Endpoints](#chrome-extensions-apis-and-endpoints)

## Manifest File

The `manifest.json` file is the configuration file for your Chrome extension. It provides important information about your extension, such as its name, version, permissions, and more.

```json
{
  "manifest_version": 3,
  "name": "My Chrome Extension",
  "version": "1.0.0",
  "description": "A brief description of your Chrome extension.",
  "icons": {
    "16": "icons/icon16.png",
    "48": "icons/icon48.png",
    "128": "icons/icon128.png"
  },
  "action": {
    "default_icon": "icons/icon.png",
    "default_popup": "popup/popup.html",
    "default_title": "Click here!"
  },
  "background": {
    "service_worker": "service-worker.js"
  },
  "content_scripts": [
    {
      "matches": ["<all_urls>"],
      "js": ["content-script.js"]
    }
  ],
  "permissions": ["activeTab", "storage"],
  "host_permissions": ["<all_urls>"],
  "options_ui": {
    "page": "options/options.html",
    "open_in_tab": true
  }
}
```
This manifest.json file uses Manifest V3, which configures a Chrome extension that:
1. Adds a toolbar button with a pop-up.
2. Runs a service worker for background tasks.
3. Injects scripts into all web pages.
4. Provides an option for user configuration

## Service Workers

Service workers are scripts that run in the background and handle various tasks, such as push notifications, background sync, and more.

```javascript
// service-worker.js

// Listen for the install event
self.addEventListener("install", (event) => {
  console.log("Service worker installed.");
});

// Listen for the activate event
self.addEventListener("activate", (event) => {
  console.log("Service worker activated.");
});

// Listen for the fetch event
self.addEventListener("fetch", (event) => {
  console.log("Intercepted a fetch request.");
});
```

## Content Script

Content scripts are JavaScript files that run in the context of web pages. They can interact with the DOM and communicate with the background script.

```javascript
// content-script.js

// Listen for the DOMContentLoaded event
document.addEventListener("DOMContentLoaded", (event) => {
  console.log("Content script loaded.");

  // Example: Modify the page title
  document.title = "Modified by Chrome Extension";
});
```

## Popup Folder

The popup folder contains the HTML, CSS, and JavaScript files for the extension's popup window.

```html
<!-- popup.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Popup</title>
  <link rel="stylesheet" href="popup.css">
</head>
<body>
  <h1>Welcome to the Popup!</h1>
  <script src="popup.js"></script>
</body>
</html>
```

```css
/* popup.css */
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  padding: 20px;
}

h1 {
  color: #333;
}
```

```javascript
// popup.js
console.log("Popup window loaded.");
```

## Options Folder

The options folder contains the HTML, CSS, and JavaScript files for the extension's options page.

```html
<!-- options.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Options</title>
  <link rel="stylesheet" href="options.css">
</head>
<body>
  <h1>Options Page</h1>
  <script src="options.js"></script>
</body>
</html>
```

```css
/* options.css */
body {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  padding: 20px;
}

h1 {
  color: #333;
}
```

```javascript
// options.js
console.log("Options page loaded.");
```

## Icons Folder

The icons folder contains the various icon sizes required for your Chrome extension.

## Chrome Extensions APIs and Endpoints

Depending on the functionality of your Chrome extension, you may need to connect with various APIs and their endpoints. Please provide more details about the required functionality, and I will update this section accordingly.

## Resources and Further Reading

- [Chrome Extension Documentation](https://developer.chrome.com/docs/extensions/)
- [Manifest File Format](https://developer.chrome.com/docs/extensions/mv3/manifest/)
- [Service Workers](https://developer.chrome.com/docs/extensions/mv3/service_workers/)
- [Content Scripts](https://developer.chrome.com/docs/extensions/mv3/content_scripts/)
- [Popup and Options Pages](https://developer.chrome.com/docs/extensions/mv3/user_interface/)
- [Icons](https://developer.chrome.com/docs/extensions/mv3/manifest/icons/)
- [APIs and Endpoints](https://developer.chrome.com/docs/extensions/reference/)
