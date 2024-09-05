# P & ID Automation Script

This project automates the process of identifying and verifying components on Piping and Instrumentation Diagrams (P&IDs) or Isometric Drawings through a series of steps involving data extraction, image processing, and optical character recognition (OCR).

## Prerequisites

- Python 3.6+
- Required Python packages: `pandas`, `openpyxl` or `xlrd` for Excel files, `PyMuPDF`, `Pillow`, `opencv-python`, `numpy`, `imutils`, `easyocr`, `argparse`

Ensure you have these libraries installed:

```bash
pip install pandas openpyxl PyMuPDF Pillow opencv-python numpy imutils easyocr argparse
```

## Setup

1. **Clone the repository:**

   ```bash
   git clone <your-repository-url>
   cd <your-repository-directory>
   ```

2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

## Usage

To run the script, use the following command:

```bash
python prog.py \
    --ScopeDocPath /path/to/your/scope_document.xlsx \
    --SheetName "Sheet1" \
    --PdfDirectory /path/to/pdf/directory \
    --PngDirectory /path/to/output/png/directory \
    --ZoomFactor 6 \
    --TemplatePath /path/to/your/template_image.png \
    --TemplateMatch_imgs_path /optional/path/to/save/template/matching/results \
    --highlighted_images_path /path/to/save/highlighted/images
```

### Command Line Arguments:

- **--ScopeDocPath**: Path to the Excel or CSV file containing scope information.
- **--SheetName**: Name of the sheet in the Excel file to read from. Defaults to the first sheet if not specified.
- **--PdfDirectory**: Directory containing all the Isometric PDF drawings.
- **--PngDirectory**: Directory where the converted PNG images will be saved.
- **--ZoomFactor**: Factor to zoom the PDF for conversion to PNG, increasing resolution. Default is 6.
- **--TemplatePath**: Path to the PNG image template you want to match in the drawings.
- **--TemplateMatch_imgs_path**: Optional path to save images showing template matching results. If not provided, results won't be saved.
- **--highlighted_images_path**: Path where images with highlighted matched regions will be saved.

## Project Structure

- `prog.py`: Main script to run the automation process.
- `infoExtract.py`: Contains function to extract information from Excel/CSV.
- `pdf2png.py`: Converts PDF files to PNG images.
- `TemplateMatching.py`: Performs template matching on images.
- `ocr.py`: Processes images with coordinates to perform OCR.
- `filtered_coordinate.py`: Filters OCR results based on predefined criteria.
- `highlighte.py`: Highlights the matched regions on images.

## Contribution

Feel free to fork this project, make improvements, or fix bugs. Please submit pull requests with clear descriptions of your changes.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Contact

For any questions or feedback, please open an issue on the GitHub repository or contact:

- Your Name: [Your Email]
- Project GitHub: [Your GitHub Repository URL]

---

**Note:** Adjust paths, names, and contact information according to your project's specifics.
