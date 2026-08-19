 performed a SQL injection UNION attack to find a column that's compatible with a string 

i first determined the column count with ORDER BY payload, then confirmed with NULLs so i can insert or retrieve data

substituted each NULL with a test string 'test' into one column at a time to know which column have data while keeping NULL to others

returned error response at the first column and 200 ok at second column The string appeared when placed in the second column, showing that column 2 is string compatible and its contents are displayed in the page
making it the column i can use to output retrieved data.

the visible column gives me the output channel needed to extract arbitrary data from the database (versions, credentials, other tables) in subsequent UNION queries.
