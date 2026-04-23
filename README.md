
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

Here are the solutions for the remaining lab questions involving XML, JavaScript DOM parsing, and Java Server Pages (JSP).

---

## 7. XML Parsing with JavaScript
**Objective:** Create an XML structure and use JavaScript to extract and display its data on a web page.

### Code (`books.html`)
```html
<!DOCTYPE html>
<html>
<body>
    <h2>Book List</h2>
    <div id="display"></div>

    <script>
        // XML String
        const xmlString = `
        <library>
            <book>
                <title>Java Programming</title>
                <author>Herbert Schildt</author>
                <price>500</price>
            </book>
            <book>
                <title>Web Technologies</title>
                <author>Jeffrey Jackson</author>
                <price>450</price>
            </book>
        </library>`;

        // Parsing XML
        const parser = new DOMParser();
        const xmlDoc = parser.parseFromString(xmlString, "text/xml");
        const books = xmlDoc.getElementsByTagName("book");
        
        let output = "<ul>";
        for (let i = 0; i < books.length; i++) {
            let title = books[i].getElementsByTagName("title")[0].childNodes[0].nodeValue;
            let author = books[i].getElementsByTagName("author")[0].childNodes[0].nodeValue;
            output += `<li><strong>${title}</strong> by ${author}</li>`;
        }
        output += "</ul>";
        document.getElementById("display").innerHTML = output;
    </script>
</body>
</html>
```

### Explanation
* **XML Structure**: A hierarchical format used to store data. Here, `<library>` is the root, and `<book>` is the child.
* **DOMParser**: A JavaScript object that converts a string containing XML into a "DOM Document" that we can navigate.
* **getElementsByTagName**: Used to grab all elements with a specific tag name, similar to how we select HTML elements.

---

## 8. JSP Greeting Program
**Objective:** Use JSP to take user input from a form and display a personalized message.

### Code (`index.jsp` & `greet.jsp`)
**index.jsp (The Form)**
```html
<form action="greet.jsp">
    Enter Name: <input type="text" name="username">
    <input type="submit" value="Greet Me">
</form>
```

**greet.jsp (The Logic)**
```jsp
<html>
<body>
    <% 
        String name = request.getParameter("username");
        out.print("<h1>Hello, " + name + "! Welcome to JSP.</h1>");
    %>
</body>
</html>
```

### Explanation
* **`request.getParameter()`**: This method retrieves the data sent from the HTML form.
* **`<% ... %>`**: These are JSP scriptlet tags. Any Java code written inside them is executed on the server.
* **Processing**: When the user clicks submit, the name is sent to `greet.jsp`, which processes it and sends back the HTML greeting.

---

## 9. JSP Visit Counter (Session Tracking)
**Objective:** Count how many times a user has visited the page during their current session.

### Code (`counter.jsp`)
```jsp
<%@ page import="java.util.*" %>
<html>
<body>
    <%
        Integer count = (Integer) session.getAttribute("visitCount");
        if (count == null) {
            count = 1;
        } else {
            count++;
        }
        session.setAttribute("visitCount", count);
    %>
    <h2>You have visited this page <%= count %> time(s) in this session.</h2>
</body>
</html>
```

### Explanation
* **Session**: A session tracks a specific user’s interaction with the website across multiple page refreshes.
* **`session.getAttribute()`**: Checks if a "visitCount" variable already exists for this user.
* **`session.setAttribute()`**: Saves the updated number back into the session memory.

---

## 10. JSP Database Connectivity (User Records)
**Objective:** Connect to a MySQL database and display a table of users.

### Code (`displayUsers.jsp`)
```jsp
<%@ page import="java.sql.*" %>
<html>
<body>
    <table border="1">
        <tr><th>ID</th><th>Name</th><th>Email</th></tr>
        <%
            try {
                Class.forName("com.mysql.cj.jdbc.Driver");
                Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "root", "password");
                Statement st = con.createStatement();
                ResultSet rs = st.executeQuery("select * from users");

                while(rs.next()) {
        %>
                <tr>
                    <td><%= rs.getInt("id") %></td>
                    <td><%= rs.getString("name") %></td>
                    <td><%= rs.getString("email") %></td>
                </tr>
        <%
                }
                con.close();
            } catch(Exception e) { out.print(e); }
        %>
    </table>
</body>
</html>
```

### Explanation
* **JDBC**: Java Database Connectivity. It requires a driver (the `Class.forName` line) to talk to the database.
* **Connection & Statement**: Establish the link and prepare the SQL command (`select * from users`).
* **ResultSet**: An object that holds the data returned from the database. We loop through it using `rs.next()` to build the table rows.
