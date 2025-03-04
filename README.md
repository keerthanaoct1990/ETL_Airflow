

# ETL_Airflow
The program collect toll data data available in different formats and consolidate it into a single file.
Aim of the program is to develop an Apache Airflow DAG that will:
1) Extract data from a csv file
2) Extract data from a tsv file
3) Extract data from a fixed-width file
4) Transform the data
5) Load the transformed data into the staging area (a folder)
Steps involved:

1. Python function 'download_dataset' to download the data set from the source to the destination.
Source: https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0250EN-SkillsNetwork/labs/Final%20Assignment/tolldata.tgz
2. Python function 'untar_dataset' to untar the downloaded data set
3. function 'extract_data_from_csv' to extract the fields Rowid, Timestamp, Anonymized Vehicle number, and Vehicle type from the vehicle-data.csv file and save them into a file named csv_data.csv
4. function 'extract_data_from_tsv' to extract the fields Number of axles, Tollplaza id, and Tollplaza code from the tollplaza-data.tsv file and save it into a file named tsv_data.csv.
5. function 'extract_data_from_fixed_width' to extract the fields Type of Payment code and Vehicle Code from the fixed width file payment-data.txt and save it into a file named fixed_width_data.csv
6. function 'consolidate_data' to creates file named extracted_data.csv by combining data from the following files:
csv_data.csv
tsv_data.csv
fixed_width_data.csv
The final csv file should use the fields in the order given below:
Rowid, Timestamp, Anonymized Vehicle number, Vehicle type, Number of axles, Tollplaza id, Tollplaza code, Type of Payment code, and Vehicle Code
7. function 'transform_data' to transform the vehicle_type field in extracted_data.csv into capital letters and save it into a file named transformed_data.csv in the staging directory.
