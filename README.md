# DataConversion_ETL
Mini project demonstrating ETL processes using PostgreSQL.

## Files Included
In here there are 4 legacy data files, and various scripts in plain text to show all queries that were ran. 

## EXTRACT
- To start, I first made up some ficticuous legacy data for customer, product, and order information.
- Then I created a database in PostgreSQL and ran a few queries to create the tables to import the legacy data.
  - Since this is "legacy" data, its messy thus I created staging tables for each dataset (customers, products, orders, and order_items) where all columns are set to TEXT. This allows for the legacy data which may contain errors such as missing values or improperly formatted data to get imported.
- Finally, I imported all of the legacy data into the database

## TRANSFORM
- Starting out I went through the data to find any missing data, nulls, incorrectly formatted phone numbers, emails, or addresses. I also looked to normalize all of the Namesand again make sure names were not formatted with first and last together and such.
- During which we found that emails, addresses, and phone numbers had issues
  - Created a view of the number of null data in each field for customer data, finding 11 missing phone numbers, and 15 missing addresses. These need to be sent to the error table immediatly as we cannot transform these items instead they need to be taken from the customer themselves. Therefore, I created the customer error table (in real world a log) where the record will be extracted and dealt with then later on inserted back when fixed. However, at the moment in order to uphold data integrity we are extracting the record and placing them into the error table.
   
## LOAD
- For this portion, I took the transformed data and loaded it into target tables such as the customer table.
