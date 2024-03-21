Para fazer rodar:
- pip install -r requirements 
- flask run --host=0.0.0.0
- export REDIS_HOST=localhost

Troubleshooting:
- sudo systemctl restart redis
- curl ip
- curl localhost
- ss -atunpp | grep 6379

Criar imagem (Dockerfile):
- FROM python:3.11
- WORKDIR /app
- COPY requirements.txt .
- COPY app.py .
- COPY templates templates/
- COPY static static/
- RUN pip install --no-cache-dir -r requirements.txt
- EXPOSE 5000
- CMD ["flask", "run", "--host=0.0.0.0"]

Buildar imagem:
- docker image build -t giropops-senhas:1.0 .

Rodar a imagem:
- docker run -d --name giropops-senhas -p 5000:5000 giropops-senhas:1.0

Resolvendo o problema do redis-host:
- docker run -d --name redis -p 6379:6379 redis

Remover todos os containers e imagem não utilizados:
- docker system prune -a

Ver logs
- docker container logs giropops-senhas
