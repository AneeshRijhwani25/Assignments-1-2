# Zeotap Assignments

This repository contains two assignments related to web development and data processing. Below are the details for each assignment.

---

## Assignment 1: Spreadsheet Application

### Getting Started

### Installation

Clone the repository:
```bash
git clone https://github.com/AneeshRijhwani25/Assignments-1-2.git
cd Assignment1
```

Run the development server:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

### Features

1. **Spreadsheet Grid**
    - **Interactive Grid**: Click on any cell to start editing its content. You can select multiple cells by clicking and dragging across the grid.
    - **Formula Bar**: A formula bar at the top of the interface allows you to enter or edit the values in the selected cells.

2. **Formula Calculations**
    - Perform common calculations on selected cells:
      - **SUM**: Adds up the values in the selected cells.
      - **AVERAGE**: Calculates the average value of the selected cells.
      - **MAX**: Finds the maximum value in the selected cells.
      - **MIN**: Finds the minimum value in the selected cells.
      - **COUNT**: Counts the number of cells with numerical data in the selection.

3. **Data Quality Operations**
    - Apply various operations to improve or clean the data:
      - **TRIM**: Removes leading and trailing spaces from text in selected cells.
      - **UPPERCASE**: Converts text to uppercase.
      - **LOWERCASE**: Converts text to lowercase.
      - **REMOVE DUPLICATES**: Removes duplicate values from the selected range.
      - **FIND AND REPLACE**: Search and replace specific text values across the selected cells.

4. **Clipboard Operations**
    - Use the **"Edit"** menu for standard clipboard actions:
      - **Cut**: Remove selected cell data and place it in the clipboard.
      - **Copy**: Copy the selected cell data to the clipboard.
      - **Paste**: Paste data from the clipboard into the selected cell(s).

5. **Export to Excel**
    - Export the spreadsheet data to an Excel file by clicking the "Save as Excel" option in the "File" menu. This allows users to download the current state of the spreadsheet in Excel format for further analysis or reporting.

6. **Dynamic Row and Column Insertion**
    - Easily add new rows and columns to the grid:
      - Hover over the row numbers or column letters to reveal a "+" button.
      - Click the "+" button to insert a new row or column where you are hovering.

### Usage

1. **Start Editing**
    - Click on any cell in the grid to begin editing the content.
    - For multiple cell selections, click and drag to select a range.

2. **Perform Calculations**
    - Select the cells you want to calculate.
    - Choose a formula (e.g., SUM, AVERAGE) from the "Formula" menu in the toolbar.

3. **Apply Data Quality Operations**
    - Select the range of cells where you want to apply data quality operations.
    - Choose the desired operation (e.g., TRIM, REMOVE DUPLICATES) from the "Data Quality" menu.

4. **Clipboard Actions**
    - Use the "Edit" menu to cut, copy, and paste data between cells.

5. **Export to Excel**
    - After making changes to the grid, you can export the data by selecting the "Save as Excel" option from the "File" menu.

6. **Insert Rows/Columns**
    - Hover over the row or column labels to reveal the "+" button.
    - Click the "+" button to insert new rows or columns as needed.

### Dependencies

This project uses the following dependencies:
- **lucide-react**: Provides icons for the toolbar.
- **next**: The Next.js framework for building React applications.
- **react**: The React library for building user interfaces.
- **react-dom**: React DOM library for managing rendering in the browser.
- **xlsx**: A library for reading and writing Excel files.
- **postcss**: A tool for transforming CSS.
- **tailwindcss**: A utility-first CSS framework for styling.

### Scripts

The following scripts are available to manage the development and deployment of the application:
- `dev`: Runs the development server.
- `build`: Builds the application for production.
- `start`: Starts the production server.
- `lint`: Lints the codebase to ensure code quality.

---

## Assignment 2: CDP Support Agent

### 📌 Overview
CDP Support Agent is a web scraping and AI-powered query system that extracts, processes, and retrieves documentation from multiple **Customer Data Platforms (CDPs)**, including **Lytics, mParticle, Segment, and Zeotap**. It enables users to search and retrieve relevant documentation efficiently by leveraging Google's **Gemini AI**.

### **🔧 Key Features**
- **Web Scraping**: Automates the extraction of documentation from various CDP platforms.
- **Data Storage & Retrieval**: Stores extracted documentation and enables keyword-based search.
- **AI-Powered Query Handling**: Uses **Gemini AI** to summarize and format responses.

### 📂 Project Structure
```
Assignment2/
├── data/
│   ├── processors/        # Scraping and text processing
│   │   ├── lytics_scraper.py
│   │   ├── mparticle_scraper.py
│   │   ├── segment_scraper.py
│   │   ├── text_processor.py
│   │   └── zeotap_scraper.py
│   ├── storage/           # Storage and retrieval
│   │   ├── __init__.py
│   │   └── document_store.py
├── services/              # AI query handling
│   ├── __init__.py
│   ├── gemini_service.py
│   └── query_handler.py
├── utils/                 # Helper functions
│   ├── __init__.py
│   └── helper.py
├── app.py                 # Main application entry point
├── requirements.txt        # Dependencies
└── .env                   # API keys and environment variables
```

### 🚀 Installation & Setup

#### **🔹 Prerequisites**
- Python 3.8+
- Virtual Environment (Recommended)
- ChromeDriver (if using Selenium for authentication)

#### **🔹 Clone the Repository**
```bash
git clone https://github.com/AneeshRijhwani25/Assignments-1-2.git
cd Assignment2
```

#### **🔹 Set Up Virtual Environment (Optional)**
```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows
```

#### **🔹 Install Dependencies**
```bash
pip install -r requirements.txt
```

#### **🔹 Set Up Environment Variables**
Create a `.env` file to store API keys:
```
GEMINI_API_KEY=your_gemini_api_key
```

### 📌 Usage

#### **🔹 Run the Application**
```bash
python app.py
```

#### **🔹 Scrape Documentation**
```bash
python data/processors/lytics_scraper.py
python data/processors/mparticle_scraper.py
python data/processors/segment_scraper.py
python data/processors/zeotap_scraper.py
```

#### **🔹 Query the Documentation**
```python
from services.query_handler import QueryHandler

query_handler = QueryHandler()
response = query_handler.handle_query("How do I set up user tracking in Segment?")
print(response)
```

### 🛠️ Troubleshooting
**Issue:** Scraper fails to extract certain pages.
- Solution: Check if the website structure has changed. Update CSS selectors accordingly.

**Issue:** Getting 403 Forbidden errors.
- Solution: Add proper headers (User-Agent, Cookies) to avoid bot detection.

**Issue:** No response from Gemini API.
- Solution: Ensure `GEMINI_API_KEY` is correctly set in `.env`.

---

### License
This project is licensed under the MIT License.

### Contact
For any questions or feedback, please contact [Aneesh Rijhwani](https://github.com/AneeshRijhwani25).
