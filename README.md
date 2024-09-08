# ETL Script for Medication Stock Management

This Python script performs Extract, Transform, Load (ETL) operations on medication stock data from an Excel file to a PostgreSQL database.

## Prerequisites

- Python 3.x
- pandas
- psycopg2
- SQLAlchemy

## Installation

1. Install the required Python packages:

```
pip install pandas psycopg2 sqlalchemy
```

2. Set up a PostgreSQL database named `db_sediaan_obat`.

## Configuration

Before running the script, update the following variables in the code:

- `file_path`: Path to your Excel file
- `year`: The year of the data (format: 'YYYY-')
- `sheet_name`: The name of the Excel sheet (usually the month name in Indonesian)
- Database connection details in the `create_engine` function

## Usage

Run the script using Python:

```
python etl_process.py
```

## Functionality

The script performs the following operations:

1. **Extract**: Reads data from a specified Excel file and sheet.
2. **Transform**: 
   - Trims the DataFrame to relevant columns
   - Cleans and renames columns
   - Adds a 'Year-Month' column
   - Calculates total usage
   - Handles missing values
3. **Load**: Inserts the transformed data into a PostgreSQL database table named 'stok_obat'.

## Output

The script will print a message indicating successful data processing and insertion, followed by the last few rows of the inserted data.

## Note

Ensure that the Excel file structure matches the expected format, with 'SISA AKHIR' as the keyword for the last relevant column.

## Troubleshooting

If you encounter any issues related to data format or database connection, check the corresponding sections in the code and adjust as needed.
