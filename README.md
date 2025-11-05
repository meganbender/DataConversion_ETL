# DataConversion_ETL
Mini project demonstrating ETL processes using PostgreSQL.

## EXTRACT
- To start, I first made up some ficticuous legacy data for customer, product, and order information.
- Then I created a database in PostgreSQL and ran a few queries to create the tables to import the legacy data.
  - Since this is "legacy" data, its messy thus I created staging tables for each dataset (customers, products, orders, and order_items) where all columns are set to TEXT. This allows for the legacy data which may contain errors such as missing values or improperly formatted data to get imported.
- Finally, I imported all of the legacy data into the database

## TRANSFORM
## LOAD
