# ID Card Generator for Word Sanctuary Global

This application automates the generation of ID cards for up to 600 people using a template image and data from an Excel spreadsheet.

## Features

- Upload an ID card template image
- Process an Excel file containing user data (names, installations, departments)
- Download passport photos from Google Drive links
- Automatically place photos and text onto the template
- Generate personalized ID cards for each person

## Installation

1. Clone this repository
2. Install dependencies:
   ```
   npm install
   ```
3. Start the application:
   ```
   npm start
   ```
4. Open your browser and navigate to `http://localhost:3000`

## Excel File Format

Your Excel file should have the following columns:

- **Name** - Full name of the person
- **Installation** - Installation information
- **Department** - Department information
- **PhotoUrl** - Google Drive link to the person's photo

## Template Image

The template image should have:

- A placeholder area for the passport photo
- Areas for text (name, installation, department)

## Adjusting for Your Template

You may need to modify the coordinates in the `createIDCard` function to match your specific template layout:

```javascript
// In app.js, find these lines and adjust as needed:
const photoX = 186; // X position of the photo placeholder
const photoY = 860; // Y position of the photo placeholder
const photoWidth = 300; // Width of the photo placeholder
const photoHeight = 300; // Height of the photo placeholder

// Also adjust the text positions if needed:
<text x="560" y="840" class="name">${name}</text>
<text x="560" y="920" class="info">${installation}</text>
<text x="560" y="1000" class="info">${department}</text>
```

## Troubleshooting

- **Google Drive Links**: Ensure your Google Drive links are set to "Anyone with the link can view"
- **Image Positioning**: If photos or text don't align properly, adjust the coordinates in the code
- **Large Batch Processing**: For very large batches, the process may take several minutes
