**Methods of Adding and Changing HTML**
### 1. **Using InnerHTML**

- `element.innerHTML = "<p>New Content</p>";`
- This replaces the entire HTML inside an element.
- Useful for dynamically updating content but can be unsafe if handling user input (risk of XSS attacks).

### 2. **Using InnerText**

- `element.innerText = "New Text";`
- Updates only the text inside an element, preserving the original structure.
- It does not interpret HTML tags.

### 3. **Using TextContent**

- `element.textContent = "New Content";`
- Similar to `innerText`, but it does not respect styling like `display: none;`.

### 4. **Using appendChild()**

- `element.appendChild(newElement);`
- Adds a new child element at the end of a parent element.
- Only works with nodes (not raw HTML strings).

### 5. **Using createElement()**

- `let newElement = document.createElement("p");`
- `newElement.textContent = "New Paragraph";`
- `document.body.appendChild(newElement);`
- Dynamically creates a new HTML element and adds it to the document.

### 6. **Using insertAdjacentHTML()**

- `element.insertAdjacentHTML("beforeend", "<p>New Paragraph</p>");`
- Adds HTML at a specific position:
    - `beforebegin`: Before the element.
    - `afterbegin`: Inside the element, before its first child.
    - `beforeend`: Inside the element, after its last child.
    - `afterend`: After the element.

### 7. **Using replaceChild()**

- `element.replaceChild(newElement, oldElement);`
- Replaces an existing child node with a new one.

### 8. **Using removeChild()**

- `parentElement.removeChild(childElement);`
- Removes a specific child element from its parent.

### 9. **Using outerHTML**

- `element.outerHTML = "<h1>New Heading</h1>";`
- Replaces the entire element itself, not just its content.

### 10. **Using setAttribute()**

- `element.setAttribute("class", "new-class");`
- Modifies or adds an attribute to an element.

### 11. **Using classList**

- `element.classList.add("new-class");`
- `element.classList.remove("old-class");`
- `element.classList.toggle("active");`
- Manipulates CSS classes dynamically.

### 12. **Using style Property**

- `element.style.color = "red";`
- `element.style.fontSize = "20px";`
- Directly modifies an element’s inline styles.

Each method is useful in different scenarios, depending on whether you need to add, modify, or remove HTML elements dynamically.