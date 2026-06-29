Netflix Dataset - Data Cleaning Project
📌 Project Overview
This project is part of my data analytics learning journey. The goal was to take a raw, messy dataset of Netflix titles (netflix_titles.csv) and clean it completely using Microsoft Excel so that it is 100% ready for analysis and making dashboards.

🛠️ Tools Used
Microsoft Excel (Advanced Filters, Find & Replace, and Go To Special tool)

Power Query (For complex data transformation and date standardization)

🔍 Steps Taken for Data Cleaning
1. Finding and Removing Duplicates
I checked the dataset for duplicate movies and TV shows. I found two types of duplicates:

Exact Duplicates: Titles like 15-Aug, 22-Jul, and Feb-09 were repeated with different show IDs. I removed the extra rows.

Fuzzy Duplicates: Some shows like Sin senos sí hay paraíso and Love in a Puff had different spellings or partial data. I kept the row with the most complete information and deleted the incomplete ones.

Special Case (Fullmetal Alchemist): I found two rows with this name, but after checking, one was a Movie (2017) and the other was a TV Show (2003). Since they were different contents, I did not delete them.

2. Fixing the "Louis C.K." Data Shift Error
While cleaning the duration column, I found a unique error. For three comedy shows by Louis C.K., the duration (like 74 min, 84 min, 66 min) was accidentally typed in the rating column, leaving the duration column blank.

Fix applied: I manually cut the duration from the rating column, pasted it into the duration column, and marked the rating as NR (Not Rated).

3. Handling Blank (Missing) Cells
Director, Cast, and Country: These columns had thousands of missing values. Deleting them would ruin the data. I noticed some cells looked blank but had hidden spaces. I cleaned them and replaced all empty cells with the word "Unknown".

Date Added: There were exactly 10 TV shows (including famous shows like Friends and Frasier) where the Netflix upload date was missing. Since putting "Unknown" in a date column breaks charts, I manually entered a default date: January 1, [Release_Year] based on the show's release year.

4. Date Format Standardization
The date_added column originally contained dates in an inconsistent text format (e.g., 'Month DD, YYYY').

To ensure consistency for time-series analysis, I utilized Power Query to convert these entries into a uniform 'DD-MM-YYYY' format.

The conversion process involved setting the Locale to 'English (United States)' to correctly interpret month names, ensuring the data is now fully optimized for professional reporting.

🎯 Final Result
After performing all the cleaning steps, I verified the entire sheet using Excel's Go To Special -> Blanks tool. The tool confirmed "No cells were found".
The dataset is now completely clean, error-free, and saved as `Netflix_Cleaned_Dataset.xlsx`.
