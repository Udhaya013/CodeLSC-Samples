# Create an AutoComplete Component with Debounce

In this blog post, we will create an AutoComplete component using vanilla JavaScript, HTML, and CSS. We will also implement a debounce function to optimize our component.

## What is Debounce?

Debounce is a programming practice used to ensure that time-consuming tasks do not fire so often. This can be particularly useful for certain events that can trigger a high frequency of function calls in a short period of time, such as scroll, resize, keyup, mousemove etc. 

## The Code

Here is the HTML code for our AutoComplete component:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Autocomplete Component</title>
    <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
    <style>
        #autocomplete-list {
            display: none;
            position: absolute;
            border: 1px solid #ccc;
            background-color: #fff;
            max-height: 200px;
            overflow-y: auto;
            z-index: 1000;
        }
        .w3-container{
            margin: 130px auto;
        }
    </style>
</head>

<body>
    <div class="w3-container w3-auto">
        <label class="w3-text-blue"><b>AutoComplete</b></label>
        <input type="text" id="autocomplete-input" class="w3-input w3-border w3-round" placeholder="Type something...">
        <ul id="autocomplete-list" class="w3-ul w3-card-4"></ul>
    </div>
</body>

</html>
```

And here is the JavaScript code with the debounce function:

```javascript
<script>
    const input = document.getElementById('autocomplete-input');
    const autocompleteList = document.getElementById('autocomplete-list');
    let debounceTimer;

    function debounce(func, delay) {
        clearTimeout(debounceTimer);
        debounceTimer = setTimeout(func, delay);
    }

    input.addEventListener('input', function () {
        const inputValue = this.value;
        autocompleteList.innerHTML = '';

        debounce(() => {
            fetch(`https://jsonplaceholder.typicode.com/posts?title_like=${inputValue}`)
                .then(response => response.json())
                .then(data => {
                    data.forEach(item => {
                        const listItem = document.createElement('li');
                        listItem.classList.add('autocomplete-item', 'w3-bar');
                        listItem.textContent = item.title;
                        listItem.addEventListener('click', function () {
                            input.value = item.title;
                            autocompleteList.innerHTML = '';
                        });
                        autocompleteList.appendChild(listItem);
                    });
                })
                .catch(error => {
                    console.error('Error fetching autocomplete data:', error);
                });

            if (inputValue === '') {
                autocompleteList.innerHTML = '';
            } else {
                autocompleteList.style.display = 'block';
            }
        }, 300); // Adjust debounce delay as needed
    });

    document.addEventListener('click', function (e) {
        if (!autocompleteList.contains(e.target) && e.target !== input) {
            autocompleteList.style.display = 'none';
        }
    });
</script>
```

## Code Explanation

Let's break down the JavaScript code:

- We declare three variables: `input`, `autocompleteList`, and `debounceTimer`. `input` is the text input field where the user types. `autocompleteList` is the unordered list (`<ul>`) where the autocomplete suggestions will be displayed. `debounceTimer` will be used to control the debounce functionality.

- The `debounce` function takes two parameters: `func` (the function to be debounced) and `delay` (the debounce delay in milliseconds). The `clearTimeout` function is used to clear any existing timer that might be running. The `setTimeout` function is then used to set a new timer that calls `func` after `delay` milliseconds.

- An event listener is added to the `input` field that triggers whenever the user types (`input` event). Inside this event listener, we get the current value of the input field and clear the `autocompleteList`.

- We use the `debounce` function to delay the execution of the code inside it. This code fetches data from an API endpoint and populates the `autocompleteList` with the fetched data. Each item in the list is an `<li>` element that, when clicked, sets the input field's value to the clicked item's title and clears the `autocompleteList`.

- If the input field is empty, the `autocompleteList` is cleared. Otherwise, the `autocompleteList` is displayed. The `300` passed to the `debounce` function is the debounce delay in milliseconds.

- Finally, an event listener is added to the document that triggers whenever the user clicks anywhere on the page. If the click is outside the `autocompleteList` and the input field, the `autocompleteList` is hidden.

## Conclusion

In this blog post, we created an AutoComplete component and implemented a debounce function to optimize our component. This component can be a great addition to your web projects, providing a better user experience by reducing the number of server requests and improving the performance of your web application. We hope this tutorial was helpful and encourage you to continue exploring the many possibilities of JavaScript! Happy coding!

### 📂 **Get the Full Source Code!** 📚Click [here](https://github.com/Udhaya013/CodeLSC-Samples/tree/main/AutoComplete-Component-with-Debounce) to **download the full source code**

---

# CodeLSC

# 🚀 **Welcome to CodeLSC - Your Ultimate Coding Hub!**

Embark on a coding journey with **CodeLSC**, your destination for insightful tutorials on **Angular**, **JavaScript**, **HTML**, **CSS**, and **Blazor**. From handling events to creating interactive web elements, we've got your coding adventure covered. Subscribe now for a front-row seat to the dynamic world of web development!

## 🌐 **Explore Further:**
Visit our YouTube: [CodeLSC Channel](https://youtube.com/shorts/eeHu7nprZtQ?si=5VZcR-PH__i33UJ4) and website: [CodeLSC Blog](https://codelsc.blogspot.com/) for additional resources, articles, and more!