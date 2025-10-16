# ThreatGuard – URL and File Threat Detector

**ThreatGuard** is a web application built with Flask that detects malicious URLs and files. It utilizes Google’s **Gemini AI** model to classify URLs as safe or malicious, and analyzes file content (PDF/TXT) to detect scam messages.

## Features:
- **File Scanner**: Detects scam messages in uploaded PDF and TXT files.
- **URL Detection**: Classifies URLs into categories like **Benign**, **Phishing**, **Malware**, and **Defacement**.
- **AI-Powered Classification**: Uses **Google's Gemini 2.5** model for text and URL analysis.

## Tech Stack:
- **Backend**: Flask (Python)
- **AI Model**: Google Gemini 2.5
- **Frontend**: HTML, CSS, and JavaScript (FontAwesome for icons)
- **Libraries**: PyPDF2 for PDF text extraction

--------------------------------------------------------------------------------------------------------------
### Steps to Run:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/threatguard.git
   cd threatguard
------------------------------------------------
2. Install dependencies:----->
    pip install -r requirements.txt
-------------------------------------------------
3. Set up Google API Key:----->

    --> Obtain your Google Cloud API Key from the Google Cloud Console.
    --> export GOOGLE_API_KEY="your-google-api-key"
    --> from here :   https://aistudio.google.com/app/api-keys
--------------------------------------------------
4. Run the Flask application:----->
    
    command--> python app.py
    -->The app will run at http://127.0.0.1:5000/


   -------------------------------------------------------------------------------------------------------------------------------

                                                             <--   HOW IT WORK --->

1. File Threat Detection:
    --> Upload a PDF or TXT file.
    --> The app extracts the text from the file and sends it to Google’s Gemini 2.5 model.
    --> The model classifies the content as either Real/Legitimate or Scam/Fake, with details on why it’s classified a certain way.

2. URL Classification:
    --> Enter a URL in the form provided.
    --> The URL is analyzed by the Gemini model, which classifies it into one of the following categories:

        --> Benign: Safe, trusted, and non-malicious websites such as google.com, wikipedia.org, amazon.com.
        --> Phishing: Fraudulent websites trying to steal personal information.
        --> Malware: Websites that distribute viruses or malware.
        --> Defacement: Websites that have been hacked and show unauthorized content.

3. AI-Based Content Classification:
    --> The AI model generates a classification based on the given text or URL, ensuring an accurate and reliable detection process.

    --> Error Handling
        --> Invalid File: The app only accepts PDF or TXT files. If an unsupported file type is uploaded, an error message is shown.
        --> Invalid URL: The app checks if the URL starts with http:// or https://. Invalid URLs will result in an error message.

    --> Solution: Ensure the file contains readable text. Empty PDFs or TXT files won’t work.