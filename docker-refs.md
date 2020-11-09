# Helpful Commands for Using Docker

## List all running Docker Containers
```docker ps | docker container ps```

## List all Docker Containers
```docker container ls -a```
(Use -aq instead of -a for listing containers by their numeric ids)

## Stop a particualar container
```docker container stop [container_id]```

## Stop all containers
```docker container stop $(docker container ls –aq)```

## Remove a Particular Container
```docker container rm [container_id]```

## Remove all containers
```docker container rm $(docker container ls –aq)```

## Run container shell (assuming the name of the container is nostalgic_lumiere):
```docker exec -ti nostalgic_lumiere /bin/bash```
