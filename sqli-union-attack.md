the lab task required me to determine the number of column returned by the query in product category filter
i injected payload 'ORDER+BY+1-- into the GET/filter?category=Pets up to four times via burp repeater 
' was first applied to close the category string
which returned 500 internal server error on the 4th payload given that the number of succesfully column returned by the query is 3
i confirmed that the injection is exploitable by applying UNION query using matching NULLs 3 times 'UNION SELECT NULL,NULL,NULL--
found out that UNION requires both queries to return the same number of columns first which is why the count must be found first.
 NULL was applied 3 times since number of column count is 3. since it is compatible with any data type, i could be able to retrieve data or swap out data from each column
 -- to comment out the remainder of the original query everything stays valid.
