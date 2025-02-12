Perform Banner Grabbing

Question: Use Netcat to perform banner grabbing on a target server running on port 80.

Answer:

1. `nc -v [target_IP] 80`
2. Send a request like: `GET / HTTP/1.1` and observe the response to identify the server and version. 

Notes: GET ... wirklich eingeben
