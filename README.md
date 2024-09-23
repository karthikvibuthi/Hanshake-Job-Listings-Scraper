
# Handshake Job Scraper

This script allows users to scrape job postings from the Handshake platform by making authenticated requests with session cookies and headers. It then parses the job data and exports it to a CSV file.

## Features
- **Fetch job postings**: Retrieves job listings from Handshake based on various filters (such as industry and work authorization preferences).
- **Extract key information**: Employer name, posting URL, job title, location, and other relevant fields.
- **Pagination**: Automatically loops through multiple pages of job postings.
- **Save to CSV**: Outputs the scraped job data to a CSV file for further use.

## Prerequisites
Before running the script, ensure you have the following dependencies installed:

- **Python 3.x**: You can download it from [python.org](https://www.python.org/downloads/).
- **Required Libraries**: The script uses the following Python libraries, which can be installed using `pip`:
    ```bash
    pip install requests
    pip install beautifulsoup4
    ```

## Usage
1. **Set up your environment**: Clone the repository and navigate to the project folder.
   ```bash
   git clone <repository-url>
   cd <project-folder>
   ```

2. **Update Cookies and Headers**:
   - **Cookies**: You need to authenticate using valid session cookies from your Handshake account. These cookies can be captured using your browser's Developer Tools (F12 -> Application -> Cookies).
   - **Headers**: You may need to include headers like `User-Agent`, `X-CSRF-Token`, and others. These can also be found in the network requests made by your browser when visiting Handshake.

   Update the `cookies` and `headers` dictionary in the script with your own values.

3. **Configure Parameters**:
   - The `params` dictionary allows you to customize the job search filters, such as job industries, sponsorship preferences, and work authorization requirements.
   - The script is currently set to fetch jobs from the "Internet & Software" industry (`job.industries[]: '1034'`). You can change these parameters based on your preference.

4. **Run the Script**:
   You can run the script using the following command:
   ```bash
   python <script_name>.py
   ```

5. **Output**:
   The scraped job listings will be saved to a CSV file named `job_listings.csv` by default. You can change the filename in the `scrape_employer_data` function if needed.



## Notes
- Make sure to replace the `cookies` and `headers` in the script with your valid session information.
- If you are scraping a large number of pages, make sure to respect the website’s rate limits to avoid getting your IP banned.

## License
This project is licensed under the MIT License.

--- 

### Optional Enhancements
1. **Error handling**: Add more robust error handling for cases where the request fails, cookies expire, or job fields are missing.
2. **Login automation**: Use Selenium to automate login and cookie extraction dynamically.
3. **Additional fields**: Extend the script to capture more job fields such as salary, job descriptions, etc.

