
# Lab Solutions: Web Development & JavaScript

## 1. Simple HTML Structure
**Objective:** Create a web page with headings, paragraphs, links, and lists.

### Code (`index.html`)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>My Basic Webpage</title>
</head>
<body>
    <h1>Welcome to Web Development</h1>
    <p>This is a paragraph demonstrating how we display text in HTML.</p>
    
    <h3>Things to Learn:</h3>
    <ul>
        <li>HTML5 Structure</li>
        <li>CSS Styling</li>
        <li>JavaScript Logic</li>
    </ul>

    <p>Visit the official documentation <a href="https://developer.mozilla.org">here</a>.</p>
</body>
</html>
```
### Explanation
* **`<!DOCTYPE html>`**: Tells the browser this is an HTML5 document.
* **`<h1>` and `<h3>`**: Heading tags used to create titles of different sizes.
* **`<ul>` and `<li>`**: Used for "Unordered Lists" (bullet points).
* **`<a>`**: The anchor tag creates a hyperlink using the `href` attribute.

---

## 2. JavaScript Data Types
**Objective:** Declare variables and display them in the console.

### Code (`datatypes.js`)
```javascript
let userName = "Alex";          // String
let age = 21;                   // Number
let isEnrolled = true;          // Boolean
let grades = [90, 85, 88];      // Array (Object)
let studentInfo = { id: 101 };  // Object

console.log("Name:", userName);
console.log("Age:", age);
console.log("Enrolled:", isEnrolled);
console.log("Grades:", grades);
console.log("ID:", studentInfo.id);
```
### Explanation
* **`let`**: A keyword to declare variables that can change.
* **Data Types**: JavaScript automatically detects if a value is text (String), a number, or a true/false value (Boolean).
* **`console.log()`**: The standard way to output data to the browser's inspection tool.

---

## 3. JavaScript Loops (1 to 10)
**Objective:** Print numbers using `for`, `while`, and `do-while` loops.

### Code (`loops.js`)
```javascript
// For Loop
console.log("For Loop:");
for (let i = 1; i <= 10; i++) {
    console.log(i);
}

// While Loop
console.log("While Loop:");
let j = 1;
while (j <= 10) {
    console.log(j);
    j++;
}

// Do-While Loop
console.log("Do-While Loop:");
let k = 1;
do {
    console.log(k);
    k++;
} while (k <= 10);
```
### Explanation
* **`for`**: Best when you know the exact number of iterations.
* **`while`**: Checks the condition *before* running the code.
* **`do-while`**: Runs the code *at least once* before checking the condition.

---

## 4. Recursive Factorial
**Objective:** Calculate factorial using a function that calls itself.

### Code (`recursion.js`)
```javascript
function getFactorial(n) {
    if (n === 0 || n === 1) {
        return 1; // Base case
    }
    return n * getFactorial(n - 1); // Recursive call
}

console.log("Factorial of 5 is:", getFactorial(5));
```
### Explanation
* **Recursion**: A function calling itself to break a problem into smaller parts.
* **Base Case**: The `if` statement stops the function from running forever once it reaches 1.
* **Logic**: $5!$ is calculated as $5 \times 4 \times 3 \times 2 \times 1 = 120$.

---

## 5. Dynamic CSS with JavaScript
**Objective:** Change style attributes via button click.

### Code (`dynamic.html`)
```html
<p id="text">Watch me change!</p>
<button onclick="updateStyle()">Change Style</button>

<script>
    function updateStyle() {
        let element = document.getElementById("text");
        element.style.color = "red";
        element.style.fontSize = "24px";
    }
</script>
```
### Explanation
* **`getElementById`**: Finds the specific HTML element by its ID.
* **`.style`**: Accesses the CSS properties of that element.
* **`onclick`**: An event attribute that triggers the JavaScript function when the button is pressed.

---

## 6. CSS Units (Absolute vs Relative)
**Objective:** Compare `px`, `%`, and `rem`/`em`.

### Code (`style.html`)
```html
<style>
    .absolute { width: 200px; background: lightblue; }
    .percentage { width: 50%; background: lightgreen; }
    .relative { width: 10rem; background: lightcoral; }
</style>

<div class="absolute">Fixed 200px</div>
<div class="percentage">Fluid 50%</div>
<div class="relative">Relative 10rem</div>
```
### Explanation
* **`px` (Pixels)**: Stays the same size regardless of the screen size.
* **`%` (Percentage)**: Changes based on the width of the parent container.
* **`rem/em`**: Changes based on the font size of the root or parent element.
