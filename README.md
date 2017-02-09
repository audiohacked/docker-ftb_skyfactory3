# Feed-The-Beast SkyFactory 3 (Minecraft 1.10.2) in a Docker Container
To pull the image:
```
docker pull audiohacked/ftb_skyfactory3:stable
```

It's highly recommended run a data container:
```
docker run --name ftb_skyfactory3_datastore audiohacked/ftb_skyfactory3:stable true
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_skyfactory3 \
    --volumes-from ftb_skyfactory3_datastore \
    -p 25565:25565 \
    -e EULA=TRUE \
    audiohacked/ftb_skyfactory3:stable
```
