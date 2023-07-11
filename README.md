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

## boolean toggle

```html
<h2>Toggle Button:</h2>
<label class="switch">
  <input type="checkbox" id="toggleButton" name="toggleButton">
  <span class="slider"></span>
</label>

```

```javascript
// Assuming you have a toggle button with id "toggleButton" in your HTML form
const toggleButton = document.getElementById("toggleButton");
const toggleStatus = toggleButton.checked ? "On" : "Off";

const toggleParagraph = new docx.Paragraph({
  heading: docx.HeadingLevel.HEADING_1,
  children: [
    new docx.Text("Toggle Button: " + toggleStatus),
  ],
});

// Add the toggle paragraph to the document
doc.sections[0].children.push(toggleParagraph);

```

## Radio buttons
```html
<h2>Radio Buttons:</h2>
<input type="radio" id="radioOption1" name="radioOptions" value="Option 1">
<label for="radioOption1">Option 1</label><br>
<input type="radio" id="radioOption2" name="radioOptions" value="Option 2">
<label for="radioOption2">Option 2</label><br>
<input type="radio" id="radioOption3" name="radioOptions" value="Option 3">
<label for="radioOption3">Option 3</label><br>

```
```javascript
// Assuming you have radio buttons with name "radioOptions" in your HTML form
const radioOptions = document.getElementsByName("radioOptions");
let selectedOption = "";

// Loop through the radio buttons to find the selected option
for (const radioOption of radioOptions) {
  if (radioOption.checked) {
    selectedOption = radioOption.value;
    break; // Exit the loop once the selected option is found
  }
}

const doc = new docx.Document({
  sections: [{
    properties: {},
    children: [
      // Other elements...

      new docx.Paragraph({
        heading: docx.HeadingLevel.HEADING_1,
        children: [
          new docx.Text("Radio Button: " + selectedOption),
        ],
      }),

      // Other elements...
    ],
  }],
});

```
