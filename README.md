# Automated Seek Job Search

This project automates the process of applying for jobs by scraping job listings, generating customised cover letters and emails, and sending applications with attachments such as resumes and cover letters.

## Features

- **Job Scraping**: Uses the Apify Seek Job Scraper to fetch job listings based on search terms.  
- **AI-Generated Cover Letters**: Customises cover letters using LLM (MetaAI), ensuring proper Australian formatting.  
- **Email Automation**: Sends job applications with attached resumes and cover letters to recruiters via Gmail.  
- **Tracking Applications**: Tracks sent applications to prevent duplicate submissions.  

## Setup Requirements

1. **Apify API Key**  
   - Create an Apify account and obtain an API key for the Seek Job Scraper.  
   - Store the API key in an `.env` file as `APIFY_KEY`.  

2. **Gmail App Password**  
   - Generate an App Password in your Google Account settings for your Gmail account.  
   - Store the app password in the `.env` file as `SENDER_PASSWORD`.  

3. **Resume Preparation**  
   - Create the following files:
     - `resume.txt`: A plain-text version of your resume, used for AI-generated content.  
     - `resume.pdf`: A PDF version of your resume, attached to job applications.  

## How to Use

1. **Clone the repository and install dependencies**:  
   ```bash
   git clone <repository-url>
   cd <repository>
   pip install -r requirements.txt
   ```
2. **Add required environment variables in a .env file**:
    ```bash
    APIFY_KEY=<Your Apify API Key>
    SENDER_MAIL=<Your Gmail Address>
    SENDER_PASSWORD=<Your Gmail App Password>
    ```
3. **Prepare your resume files**:
    - Ensure `resume.txt` and `resume.pdf` exist in the root directory.
    - Update the `YOUR_NAME` variable in the script with your name.
4.
    **Run the application**:
    ```bash
    python3 main.py
    ```

## Customisation

- Modify the `searches` list in the `main()` function to include specific job search terms.  
- Update the `run_config` dictionary to adjust scraping parameters such as job location, category, and sorting.  

## Notes

- Ensure your Gmail account has secure app access enabled or app-specific passwords configured.  
- Applications are tracked in `applied.csv` to avoid sending duplicates.  