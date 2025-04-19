**Customizing PDF Design in Node.js using PDFKit**

### 1. **Setting Page Size and Margins**

- Default size: **Letter (8.5in × 11in)**
    
- Customize using options:
    

```javascript
const doc = new PDFDocument({
    size: 'A4',   // 'Letter', 'A4', 'Legal' or [width, height]
    margins: { top: 50, left: 50, right: 50, bottom: 50 }
});
```

---

### 2. **Adding Text with Styles**

```javascript
doc.font('Helvetica')
   .fontSize(20)
   .fillColor('blue')
   .text('Hello, PDFKit!', 100, 100, { align: 'center' });
```

- **Bold or Italic:** `Times-Bold`, `Times-Italic`
    
- **Custom Fonts:** `doc.font('path/to/custom-font.ttf')`
    

---

### 3. **Adding Headers and Footers**

```javascript
// Header
doc.fontSize(12).text('My PDF Title', { align: 'center' });

// Footer with page number
doc.text(`Page ${doc.page.number}`, 50, doc.page.height - 30, { align: 'center' });
```

---

### 4. **Working with Colors & Backgrounds**

```javascript
// Text Color
doc.fillColor('#ff0000').text('Red Text', 100, 150);

// Background Bar
doc.rect(0, 0, doc.page.width, 50).fill('#cccccc');
```

---

### 5. **Adding Images**

```javascript
doc.image('path/to/image.jpg', 50, 50, { width: 200, height: 100 });
```

To center an image:

```javascript
const imgWidth = 200;
const imgX = (doc.page.width - imgWidth) / 2;
doc.image('image.png', imgX, 100, { width: imgWidth });
```

---

### 6. **Creating Tables (Manual)**

```javascript
const startX = 50, startY = 300, rowHeight = 30;
doc.text('Name', startX, startY).text('Age', startX + 200, startY);
const people = [{ name: 'Alice', age: 25 }, { name: 'Bob', age: 30 }];
people.forEach((person, i) => {
    let y = startY + (i + 1) * rowHeight;
    doc.text(person.name, startX, y).text(person.age.toString(), startX + 200, y);
});
```

---

### 7. **Adding Links**

```javascript
doc.text('Visit Google', 100, 400)
   .underline(100, 400, 100, 20)
   .link(100, 400, 100, 20, 'https://www.google.com');
```

---

### 8. **Drawing Shapes**

```javascript
// Line
doc.moveTo(50, 250).lineTo(550, 250).stroke();

// Circle
doc.circle(300, 300, 50).stroke();

// Filled Rectangle
doc.rect(100, 100, 200, 50).fill('#ff9900');
```

---

### 9. **Multi-column Layout**

```javascript
doc.text('Column 1 text...', 50, 500, { width: 250, align: 'left' });
doc.text('Column 2 text...', 300, 500, { width: 250, align: 'right' });
```

---

### 10. **Save & Export PDF**

```javascript
doc.pipe(fs.createWriteStream('custom-styled.pdf'));
doc.end();
```

---

### **Complete Custom PDF Example**

```javascript
const PDFDocument = require('pdfkit');
const fs = require('fs');

const doc = new PDFDocument({ size: 'A4', margins: { top: 50, left: 50, right: 50, bottom: 50 } });
doc.pipe(fs.createWriteStream('styled.pdf'));

// Header
doc.fontSize(16).fillColor('blue').text('My Custom PDF', { align: 'center' });

// Background
doc.rect(0, 50, doc.page.width, 30).fill('#eeeeee');

// Image
doc.image('logo.png', 50, 100, { width: 100 });

// Table
const startX = 50, startY = 200, rowHeight = 30;
doc.text('Name', startX, startY).text('Age', startX + 200, startY);
const people = [{ name: 'Alice', age: 25 }, { name: 'Bob', age: 30 }];
people.forEach((person, i) => {
    let y = startY + (i + 1) * rowHeight;
    doc.text(person.name, startX, y).text(person.age.toString(), startX + 200, y);
});

// Page Number
doc.text(`Page ${doc.page.number}`, 50, doc.page.height - 30, { align: 'center' });

doc.end();
```

---

### **Summary of Customization Options**

|Feature|Code Snippet|
|---|---|
|**Page Size & Margins**|`{ size: 'A4', margins: { top: 50, left: 50 } }`|
|**Fonts & Text Styles**|`.font('Helvetica').fontSize(20).fillColor('blue')`|
|**Headers & Footers**|`doc.text('Page 1', 50, doc.page.height - 50, { align: 'center' });`|
|**Images**|`doc.image('path.jpg', 50, 50, { width: 200 })`|
|**Shapes**|`doc.rect(100, 100, 200, 50).fill('#ff9900');`|
|**Links**|`.text('Click', 100, 400).link(100, 400, 100, 20, 'https://google.com')`|

---

### **Conclusion**

This guide provides everything needed to **customize a PDF in Node.js using PDFKit**. Let me know if you need **specific layouts, advanced designs, or troubleshooting help!** 🚀