# OCR_SBA_Data_Extractor
An OCR tool to extract data (credit score, debt-to-income ratio, annual revenue, applicant name) from SBA loan documents using Tesseract and Python.

## Features
Preprocesses scanned SBA loan documents for better text recognition.
Extracts text using Tesseract OCR.
Parses key fields like Credit Score, Debt-to-Income Ratio, Annual Revenue, and Applicant Name.

## Requirements
To run this project, you’ll need:

Python 3.x
Libraries: opencv-python, pytesseract, pillow, matplotlib
Tesseract OCR installed:
Windows: Download from Tesseract at UB Mannheim (github.com/UB-Mannheim/tesseract/wiki) and install (e.g., to C:\Program Files\Tesseract-OCR\tesseract.exe).
Mac: brew install tesseract
Linux: sudo apt-get install tesseract-ocr
Install Python dependencies with: pip install opencv-python pytesseract pillow matplotlib

## Usage
Open in Jupyter:
Launch Jupyter Notebook: jupyter notebook
Navigate to the folder containing OCR_SBA_Data_Extractor.ipynb.
Open the notebook and run all cells.

Sample Image:
The notebook expects an image named sba_loan_doc.png in the same folder.

## Adding and Moving Sample Images
To use your own SBA loan document:

Prepare Your Image:

Scan or save your SBA loan document as a .png file (e.g., my_loan_doc.png).
Ensure text is legible (clear contrast, no heavy distortion).
Move the Image:
Place it in the same folder as OCR_SBA_Data_Extractor.ipynb.
Windows: Drag the file into the folder (e.g., C:\Users\OCR_SBA_Data_Extractor), or use: move C:\path\to\my_loan_doc.png C:\Users\OCR_SBA_Data_Extractor\
Mac/Linux: Use: mv /path/to/my_loan_doc.png /path/to/OCR_SBA_Data_Extractor/

Update the Notebook:
Open OCR_SBA_Data_Extractor.ipynb in Jupyter.
Find the line in Cell 2 and Cell 5: sample_image = "sba_loan_doc.png"
Change it to your file name: sample_image = "my_loan_doc.png"
Save and run the notebook.
Test with Included Sample:
sba_loan_doc.png is included in this repo as a sample. Run the notebook as-is to see it in action.

## Output
The notebook will:

Display the preprocessed image.
Print the extracted text.
Output a dictionary with parsed data, e.g.: {'credit_score': 720, 'dti_ratio': 30.0, 'annual_revenue': 500000.0, 'applicant': 'John Doe'}
Notes
Adjust regex patterns in Cell 4 (parse_loan_data) if your document labels differ (e.g., "DTI" instead of "Debt-to-Income Ratio").

For large scanned images, preprocessing may need tweaking (e.g., adjust fx, fy in cv2.resize).

Enjoy extracting SBA loan data with ease!
