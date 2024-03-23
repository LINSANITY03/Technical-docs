# Zevero-Emission-Data-Quality

Zevero deals with the confidential and sensitive data from its client for correct emission report. Some of the ways we can improve this experience are:

1. Before inserting data into the database, validate the input and provide proper message when validation fails.
2. Mostly inputs are added in bulks using sql or csv files which can contains duplicate. So, create unique constraints or mechanisms to capture such records.
3. Ensure foreign keys constraint are valid using manual or automated checking.
4. Add a foreign key actions for foreign key constraints such that updates are done automatically maintaining data consistency across the Emission table.
