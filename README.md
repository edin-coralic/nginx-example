Run with `docker-compose up -d` and then visit website:
- `http://localhost/booking/` - or any "subfolder" for requests to vue instance
- `http://localhost/` - for requests to python instance


For testing purposes:

- test if split ratio is "ok"? Following command will make n-requests:

	```bash
	for x in {1..100}; do curl -sI http://localhost/$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1)/ | tail -3; done;
	```

- test if cookie is set correctly, and successfully read on next requests?

	```bash
	for x in {1..100}; do curl -sI -b cookie.txt -c cookie.txt http://localhost/$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1)/ | tail -3; done;
	```
