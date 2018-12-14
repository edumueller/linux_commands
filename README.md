# linux_commands

## Find and remove files matching a pattern:

With -delete:
```find /path/to/directory -type f -name '*[0-9]x[0-9]*[0-9]x[0-9]*.jpg' -delete```

With rm:
```find /path/to/directory -type f -name '*[0-9]x[0-9]*[0-9]x[0-9]*.jpg' -exec rm {} +```

# Docker

## List Docker Containers
```docker ps```

## Docker Container Interactive Cmd
```docker exec -it <nome_do_container> /bin/bash```

(transbrasa_web_1_138077b0c51d)
