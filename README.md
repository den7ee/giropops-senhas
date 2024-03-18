Para fazer rodar:
- pip install -r requirements 
- flask run --host=0.0.0.0
- export REDIS_HOST=localhost

Troubleshooting:
- sudo systemctl restart redis
- curl ip
- curl localhost
- ss -atunpp | grep 6379
