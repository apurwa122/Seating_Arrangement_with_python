# Seating_Arrangement_with_python

Examination Seating Arrangement Generator(tools)
Python
OpenPyXL
Pandas

A Python application to automatically generate optimized seating arrangements for university examinations based on room capacities, student enrollments, and examination schedules.

Features
1. Room Allocation: Automatically assigns students to rooms based on capacity
2. Timetable Integration: Processes date-wise and session-wise exam schedules
3. Clash Detection: Identifies students scheduled for multiple exams simultaneously
4. Multiple Output Formats: Generates both per-session files and consolidated reports
5. Customizable Parameters: Supports sparse/dense seating with buffer capacity

Requirements
Python 3.7+

Required packages:
pip install pandas openpyxl xlsxwriter

Input Files
timetable.xlsx - Exam schedule with columns:
Date: Exam date (YYYY-MM-DD)
Session: "Morning" or "Evening"
Course: Course code

course_rolls.xlsx - Course enrollments with columns:
Course: Course code
RollNo: Semicolon-separated roll numbers (e.g., "101;102;103") or single values

room_capacities.xlsx - Room information with columns:
Room: Room identifier (e.g., "A-101")
Capacity: Maximum seating capacity
Building: (Optional) Building identifier

roll_names.xlsx (Optional) - Student names with columns:
RollNo: Student roll number
Name: Student name

Usage
python seating_arrangement.py [--buffer BUFFER] [--mode {Dense,Sparse}]
Options:
--buffer: Number of buffer seats to leave in each room (default: 0)

--mode: Seating density mode - "Dense" or "Sparse" (default: "Dense")

Output
The program generates:
1. Individual exam room files in format:
DD_MM_YYYY_COURSE_ROOM_session.xlsx
Contains student lists with roll numbers and names
Includes sections for TAs and invigilators
Properly formatted headers

2. Log files:
errors.txt: Detailed error logs
Console output: Progress information

3. Customization
To modify the output format:

Edit the generate_exam_sheet() method in the code
Adjust column widths, headers, or formatting as needed

4. Troubleshooting
Common issues and solutions:

A. "int object has no attribute 'split'
Ensure all roll numbers in course_rolls.xlsx are either:
Semicolon-separated strings ("101;102;103")
OR individual numbers/strings (will be automatically handled)

B. Missing student names
Verify roll_names.xlsx contains all roll numbers and matches exactly

C. Room allocation failures
Check room capacities are sufficient for student numbers

*License*
This project is open-source and available under the MIT License.

*Support*
For issues or feature requests, please open an issue on GitHub.
