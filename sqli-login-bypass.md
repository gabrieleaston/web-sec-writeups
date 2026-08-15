password bypass with WHERE clause
applied payload administrator'-- to username field
used a single string to close out the username query and the applied -- to comment out the query that comes after it leaving the password unknown
i realized that the login form required a non empty password before it would submit. because i left it empty at first which blocked my submission entirely meaning the request never reached the server side. so i entered a single space allowing the request through. the password value itself was irrelevant to the attack since it fell inside the portion commented out by --, so the server never evaluated it. 
