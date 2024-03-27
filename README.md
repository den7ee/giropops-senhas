Buildar imagem:
- docker image build -t giropops-senhas:1.0 .

Rodar os containers:
- docker container run -d -p 6379:6379 --name redis redis
- docker container run -d -p 5000:5000 --name giropops-senhas --env REDIS_HOST=LOCALHOST giropops-senhas:1.0

Troubleshooting:
- sudo systemctl restart redis
- curl ip
- curl localhost
- ss -atunpp | grep 6379

Abrir um shell dentro do container:
- docker exec -ti container-id bash

Remover todos os containers e imagem não utilizados:
- docker system prune -a

Ver logs
- docker container logs giropops-senhas

Localizando IP do container
- docker container inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' [container_name|id]
