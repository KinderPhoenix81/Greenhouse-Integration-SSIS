# Greenhouse-Integration-SSIS

## Project Features
- 2 Packages
  - Export database data to flat files: TextFileExport.dtsx
  - Import flat file data to a database: TextFileImport.dtsc
- Log file created after each package run
  - Timestamps
  - User & machine details
  - Package details
  - Itemized row counts for each table

## Project Details
- SSIS packages created using Visual Studio 2022
- Database created in SQL Server Management Studio (SSMS) 2021
- All resulting files from exports and logs go into the respective _ExportFiles & _SummaryLogs folders
- Existing .csv files in the _ImportFiles folder are used in the TextFileImport package
- Variables & expressions are used to determine file names and file paths of resulting files and connection files

## Project Setup
- To run the TextFileExport package:
  - Create a SSMS database with the name of [Greenhouse]
  - Use the sql file located under _SQLServerQueries to create appropriate table schema
  - Open each .csv file in _SampleDataFiles using Excel, and copy the data for each file into the respective table
    - Use 'Edit Top 200 Rows' to do this effectively
  - Change the project parameter BaseFolderParam in Project.params to reference where you installed the project files
    - The sample one I used was my documents folder, so this allows the flat file connections to know where to look for your connections

- To run the TextFileImport package:
  - Ensure the database of [Greenhouse] is created with proper schema
  - Ensure the project parameter of BaseFolderParam is modifed to match the install location of this project
    - This will not work without it modified

## Screenshots
*Note: Errors are present solely due to staging file paths for github repository*
![SSIS Export Package Screenshot](https://github.com/user-attachments/assets/3b439857-2184-457e-a0c2-4ebeebeaf0e5)

*Figure 1: SSIS Export Package – displaying scripting user variables and transaction-forced export tasks.*

![SSIS Import Package Screenshot](https://github.com/user-attachments/assets/6b4982dc-400b-4e46-9ee7-61ae8246281a)

*Figure 2: SSIS Import Package – displaying user variables and transaction enforced import tasks, along with a log file.*

## License
Released under the **MIT License** © 2025 Alex Allen
