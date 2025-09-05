📄 Document Scanner using OpenCV

This project implements a Document Scanner that detects documents from images or webcam feed, applies perspective transformation, and outputs a neatly scanned version.
It works similar to how mobile scanner apps (like CamScanner) process documents.

🚀 Features

Real-time scanning via webcam or from an image file.

Contour detection to find the largest quadrilateral (document).

Perspective warp to get a top-down view of the document.

Adaptive thresholding for a clean "scanned" effect.

Adjustable Canny edge thresholds with trackbars.

Save scanned documents with a single key press.

📂 Project Structure
DocumentScanner/
│── main.py           # Main script (document scanner logic)
│── utlis.py          # Helper functions (stacking, contour detection, trackbars, etc.)
│── 1.jpg             # Sample test image
│── Scanned/          # Folder where scanned outputs are saved
│── README.md         # Documentation

⚙️ Installation

Clone the repository and install dependencies:

git clone https://github.com/Mosensei7/DocumentScanner.git
cd DocumentScanner
pip install -r requirements.txt

requirements.txt
opencv-python
numpy

▶️ Usage

Run the scanner:

python main.py

Options:

webCamFeed = True → use webcam for real-time scanning

webCamFeed = False → load from image (pathImage = "1.jpg")

Controls:

Adjust threshold values using trackbars (Threshold1, Threshold2) for best edge detection.

Press 's' to save the scanned document into the Scanned/ folder.

📊 Output

The program shows a stacked view of all stages:

Original

Grayscale

Edge detection

Contours

Biggest contour

Warped (scanned) document

Final processed output

Example (screenshot):

🛠️ How It Works

Capture image from webcam or file.

Apply grayscale + blur + Canny edge detection.

Find all contours and select the largest quadrilateral (assumed to be document).

Reorder points for consistent perspective transformation.

Apply warp perspective to flatten document.

Use adaptive thresholding to enhance scanned look.

Save final output on key press.

✨ Future Improvements

Auto-adjust threshold values (remove need for trackbars).

Add OCR (Optical Character Recognition) support with Tesseract.

Detect and crop multiple documents in one frame.

Mobile app version with Flutter/Kivy.

📜 License

This project is licensed under the MIT License.

🔗 Author: Mohsen Ibrahim
