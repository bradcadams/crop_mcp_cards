# Crop MCP Character Cards
A simple Python notebook to export Marvel Crisis Protocol character cards from print and play PDFs released by Atomic Mass Games. Exported character cards can be printed as 4x6 photos.

## Inputs

In the variables section of the notebook, please review/update the following inputs:

- pdf_path - path to the PDF file containing the character cards.
- names_file - path to a tab-delimited text file that contains page numbers and character names.
- output_dir - path to the directory where jpegs of the character cards will be saved.

Updated character cards can be found on the [AMG](https://www.atomicmassgames.com/mcp-rules/) website. The names_file is expecting a tab-delimited text file without a header row containing a page number and character name. Output files will follow the naming convention *Character Name_healthy.jpeg* and *Character Name_injured.jpeg*.

Example names_file:

```
1	Dormammu
2	Cassandra Nova
3	Sentinel MK4
```

The coordinates for the card images can also be updated if they do not export correctly. After updating the coordinates, make sure the width to height ratio is 1.5 to ensure clean printing.

## Development and Testing

This notebook was developed and tested on macOS Tahoe 26.5.1 using Python 3.14. I used Claude to help identify the Python functions and packages to convert PDF to JPEG and crop the images.

## Requirements

This notebook requires two additional Python packages:

- Pillow - Fork of the Python Imaging Library (PIL) https://github.com/python-pillow/Pillow/
- pdf2image - Converts a PDF to a PIL image object. https://github.com/Belval/pdf2image

pdf2image requires that [*poppler*](https://poppler.freedesktop.org) be installed on the system. Instructions on how to install Poppler for your operating system are included in the pdf2image GitHub readme. On MacOS, use brew to install poppler:

```bash
brew install poppler
```

