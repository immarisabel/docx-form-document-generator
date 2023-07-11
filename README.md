# docx-form-document-generator
just a useful script to make documents from forms

## dropdown menus

```javascript
// Assuming you have a dropdown menu with id "dropdownInput" in your HTML form
const dropdownInput = document.getElementById("dropdownInput");
const selectedOption = dropdownInput.value;

const dropdownOptions = [
  "Option 1",
  "Option 2",
  "Option 3"
];

const dropdownText = dropdownOptions[selectedOption];

const dropdownParagraph = new docx.Paragraph({
  heading: docx.HeadingLevel.HEADING_1,
  children: [
    new docx.Text("Dropdown: " + dropdownText),
  ],
});

// Add the dropdown paragraph to the document
doc.sections[0].children.push(dropdownParagraph);

```
