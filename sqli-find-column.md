 performed a SQL injection UNION attack to find a column that's compatible with a string 

i first determined the column count with ORDER BY payload which returned 3, then confirmed with NULLs so i can insert or retrieve data

substituted each NULL with a test string 'test' into one column at a time '+UNION+SELECT+'test'+NULL,+NULL-- to know which column have data while keeping NULL to others. but i was given a specific string to use '0oZFXv' for retrieval 

returned error response at the first column and 200 ok at second column the string appeared when placed in the second column, showing that column 2 is string compatible and its contents are displayed in the page
making it the column i can use to output retrieved data.

now that i know the visible column that contains data i can extract arbitrary data from the database like credentials and other tables in subsequent UNION queries.
