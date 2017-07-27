# Feed-The-Beast SkyFactory 3 (Minecraft 1.10.2) in a Docker Container
To pull the image:
```
docker pull audiohacked/ftb_skyfactory3:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_skyfactory3_data
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_skyfactory3 \
    --volume minecraft_ftb_skyfactory3_data:/minecraft/world \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_skyfactory3:stable
```
