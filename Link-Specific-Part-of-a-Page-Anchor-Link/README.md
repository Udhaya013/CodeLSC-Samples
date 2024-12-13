### How to Link to a Specific Part of a Page (HTML Anchor Link)

Creating links to specific parts of a webpage is a fundamental feature of HTML that enhances user navigation. These are called *anchor links*, and they are especially useful for lengthy articles or one-page websites where users need quick access to specific sections.

To get started quickly on Link to a Specific Part of a Page (HTML Anchor Link), watch this video:
[![CodeLSC YouTube](https://img.youtube.com/vi/KMDB5YLuQlg/0.jpg)](https://www.youtube.com/watch?v=KMDB5YLuQlg)

Here’s a step-by-step guide:

---

#### 1. **Define the Target Section**
First, identify the section of the page you want to link to. Assign an `id` attribute to that section. The `id` should be unique within the page.

```html
<h2 id="contact">Contact Us</h2>
<p>If you have any questions, feel free to reach out via email or phone.</p>
```

---

#### 2. **Create the Anchor Link**
Use an `<a>` tag with the `href` attribute set to `#id` (where `id` matches the target section’s `id`).

```html
<a href="#contact">Go to Contact Section</a>
```

When this link is clicked, the browser scrolls directly to the element with the `id="contact"`.

---

#### 3. **Optional: Add Smooth Scrolling**
Modern web pages often implement smooth scrolling for a better user experience. This can be done with CSS:

```css
html {
    scroll-behavior: smooth;
}
```

Add this CSS rule to your stylesheet, and clicking the anchor link will result in a smooth scroll effect.

---

#### 4. **Using Anchor Links Across Pages**
To link to a specific section on another page, include the page's URL followed by `#id`:

```html
<a href="about.html#team">Meet Our Team</a>
```

This will navigate to the "team" section on the `about.html` page.

---

### Summary
Anchor links make your website more user-friendly by allowing visitors to jump directly to the information they need. By using the `id` attribute and properly linking with the `href` attribute, you can easily create these useful navigation tools. For added polish, use CSS to enable smooth scrolling.

Happy coding! 😊

### 📂 **Get the Full Source Code!** 📚Click [here](https://github.com/Udhaya013/CodeLSC-Samples/tree/main/AutoComplete-Component-with-Debounce) to **download the full source code**

---

# CodeLSC

# 🚀 **Welcome to CodeLSC - Your Ultimate Coding Hub!**

Embark on a coding journey with **CodeLSC**, your destination for insightful tutorials on **Angular**, **JavaScript**, **HTML**, **CSS**, and **Blazor**. From handling events to creating interactive web elements, we've got your coding adventure covered. Subscribe now for a front-row seat to the dynamic world of web development!

## 🌐 **Explore Further:**
Visit our YouTube: [CodeLSC Channel](https://youtube.com/shorts/eeHu7nprZtQ?si=5VZcR-PH__i33UJ4) and website: [CodeLSC Blog](https://codelsc.blogspot.com/) for additional resources, articles, and more!