<img src="https://raw.githubusercontent.com/Udhaya013/CodeLSC-Samples/main/Detect-Bowser-Online-Offline-Status/Browser's-Network-Status-JavaScript.png" title="Browser's Online/Offline Status" style="display: block; margin-left: auto; margin-right: auto; margin-bottom: 5%; width: 40%;" />

# Checking Browser's Network Status with JavaScript

In this guide, we'll explore how to determine if the browser is online or offline using JavaScript. This is an essential aspect of web development as it enables applications to adjust to the user's network connectivity status.

## Tools for Checking Browser's Network Status
The main tool used in this code is the `navigator.onLine` property provided by the Web API. The `navigator.onLine` property is a read-only property that returns a Boolean value `true` if the user's browser is online, and `false` if the browser is offline. This property is part of the Navigator interface and is updated whenever the user's system goes online or offline.

## How to Implement

## Step 1: Create HTML

Firstly, we need to create the HTML elements that we will use in our JavaScript code. Here's an example:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Check Browser's Network Status | CodeLSC</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Check If the Browser is Online or Offline with JavaScript | CodeLSC</h1>
    <hr />
    <button class="button" onclick="checkNetworkStatus()">Try it</button>
    <h3 id="networkStatus" class="glow"></h3>
</body>
</html>
```

In the above code, we have a button that, when clicked, will trigger the `checkNetworkStatus()` JavaScript function. We also have a `h3` element where we will display the network status.

## Step 2: Implement JavaScript

Next, we implement the JavaScript function that will check the network status:

```javascript
<script>
    function checkNetworkStatus() {
        var networkStatus = navigator.onLine ? "The browser is Online" : "The browser is Offline";
        document.getElementById("networkStatus").innerHTML = networkStatus;
        if (navigator.onLine) {
           // Additional code here
        }
    }
</script>
```

In the `checkNetworkStatus()` function, we use the `navigator.onLine` property to check the browser's network status and update the `h3` element to display this status. If the browser is online, it will execute the code inside the `if` block. Currently, there's a comment indicating that additional code can be added here. This is where you can add any extra functionality that should be executed when the browser is online.

And that's all! You can now determine the online or offline status of a browser. You can try this example yourself in your own HTML file. Just copy the HTML and JavaScript code into your file, open it in a web browser, and click the button to see the network status.

## Conclusion
Knowing the online or offline status of a browser is vital for building robust web applications that can handle network fluctuations. The `navigator.onLine` property offers a simple and effective way to achieve this. This code serves as an excellent starting point for developers looking to enhance their applications with network connectivity awareness.

### 📂 **Get the Full Source Code!** 📚Click [here](https://github.com/Udhaya013/CodeLSC-Samples/tree/main/Detect-Bowser-Online-Offline-Status) to **download the full source code**

---

# CodeLSC

# 🚀 **Welcome to CodeLSC - Your Ultimate Coding Hub!**

Embark on a coding journey with **CodeLSC**, your destination for insightful tutorials on **Angular**, **JavaScript**, **HTML**, **CSS**, and **Blazor**. From handling events to creating interactive web elements, we've got your coding adventure covered. Subscribe now for a front-row seat to the dynamic world of web development!

## 🌐 **Explore Further:**
Visit our YouTube: [CodeLSC Channel](https://youtube.com/shorts/eeHu7nprZtQ?si=5VZcR-PH__i33UJ4) and website: [CodeLSC Blog](https://codelsc.blogspot.com/) for additional resources, articles, and more!