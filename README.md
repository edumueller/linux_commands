# linux_commands

## Find and remove files matching a pattern:

With -delete:
```find /path/to/directory -type f -name '*[0-9]x[0-9]*[0-9]x[0-9]*.jpg' -delete```

With rm:
```find /path/to/directory -type f -name '*[0-9]x[0-9]*[0-9]x[0-9]*.jpg' -exec rm {} +```

## Find out the location of the php.ini you are currently using
```php -i | grep "Loaded Configuration File"```

# Docker

## List Docker Containers
```docker ps```

## Docker Container Interactive Cmd
```docker exec -it <nome_do_container> /bin/bash```

(transbrasa_web_1_138077b0c51d)

## Docker Logs

Exibindo logs.. 

Em tempo real: ```docker logs <container_name> -f -t --tail 100```

Entre um horário: ```docker logs <container_name> -t --since 2019-12-11T11:21:50 --until 2019-12-11T11:22:05```

OBS: O horário é horário brasileiro +3 horas.

# AWS
- [Documentação AWS CLI](https://docs.aws.amazon.com/cli/index.html)

## S3
No s3 existe mais de uma possiblidade de manipular os arquivos, tanto direto pelo aws cli que precisa ser instalado, disponibilizando o comando aws (Exemplo: ```aws [options] <command> <subcommand> [parameters]```) quanto através de apis mais específicas, como por exemplo a S3api abaixo.

### S3api
- [Documentação S3api:](https://docs.aws.amazon.com/AmazonS3/latest/API/RESTObjectGET.html)

- Comando que lista os objetos do bucket S3, 1000 a 1000:
```aws s3api list-objects --bucket bucket-name```

- Outra forma de contar a listagem utilizando o summarize do aws cli:
```aws s3 ls s3://bucket-name/ --recursive --summarize | grep "Total Objects:"```

- Encontrar um arquivo num caminho no S3: 
```aws s3 ls s3://bucket-name/Folter1/Folter2/Folder3/ | grep <partial-text-to-be-found>```

- Fazer download de um arquivo do S3 (ou upload invertendo a ordem dos caminhos):
```aws s3 cp s3://bucket-name/Folter1/Folter2/Folder3/s3-filename.txt Folder2/Folter3/local-filename.txt```
