# SCAMP-C6-Assessment

# ASK
## Task  
Study the details of the dataset and find out which industry has the highest number of fake job postings 

### Deliverables  
- Graph representing industry with highest number of fake job postings
- Summary of Analysis
- Details of Data Cleaning

# PREPARE
Dataset is made available by She Code Africa has been downloaded, and stored in Excel files for Analysis.

# PROCESS
## Clean the dataset
1. Remove Duplicates
    - Select the unique identifier column “job_id”
    - Click Home > Conditional Formatting > Highlight Cells Rules > Duplicate Values
    - Select “job_id”
    - Click Home > Sort & Filter > Filter
    - Click the filter slice on “job_id” to filter by color
Result: There are no highlighted cells. That means no duplicate entries.

2. Remove Irrelevant Data
Fake job postings = Fraudulent job postings
    - Add a filter to “fraudulent”
    - Assuming 0 is False and 1 is True, select 1
    - Copy and paste filtered data to new worksheet.

3. Structural Errors
    - Add a filter to “title”. Notice the inconsistent capitalization and job titles attached with salary details.
    - In “title” column, convert observations to proper case using =PROPER() function
    - Extract salary details found in title and fill in corresponding “salary_range” column
    - Create a column “country”, extract the country name from each ISO code in “location”
    - Replace values in “location” with values in “country”
    - Format “salary_range” to currency as Dollar
    - In “company_profile”, fix all imported special characters using Find & Replace
    - Use =TRIM() function to remove trailing spaces from “company_profile”
    - Add a filter to “industry”. Notice “industry” has similar observations with different naming conventions
    - Update observations to singular naming conventions and correct typos
    - Industry should be based on “company_profile”,  but some industries aren’t matching company profiles
    - Review each industry and ensure they are matching information on “company_profile”

4. Missing Data
    - Check for missing data within the industry column by adding a filter and checking for blanks
    - Attempt to fill blank cells with information from “company_profile”. 
    - Delete blank cells that cannot be filled with information in “company_profile”
    - Check for blank cells in the remaining columns in the spreadsheet and fill in n/a (not available)


# ANALYZE
- Create a new column in the spreadsheet, “frequency”
- Calculate the number of times each industry appears using  the COUNTIF function. For example =COUNTIF (P2:P867, P2)
- Drag formula across column
- Insert a Pivot Table
- Add “industry” to rows, and frequency to Values.
- Set value field to be summarized by Count
- Click on the pivot table and insert pivot chart.
- Select Clustered Column Chart
- Customize chart as displayed on worksheet.

# SHARE
This is an [excel workbook](https://github.com/Jen-Ashishali/SCAMP-C6-Assessment/blob/main/fake_job_postings.xlsx), with a chart representing the fake job postings. Kindly view worksheet in editing mode for best visualization experience. 
