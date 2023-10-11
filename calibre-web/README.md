If you run into **Error 500 - Internal Server Error** after the installation, and find that `calibre-web` is unable to find the `metadata.db` file in `/books`

Download the `metadata.db` file from this repository and follow these steps:

Create /books folder on your container and chmod

```bash
docker exec -it CONTAINER_ID mkdir /books
docker exec -it CONTAINER_ID chmod a+w /books
```

Place the metadata.db file on the /books path and modifty to be writeable
```bash
docker cp /path/METADATA.DB.FILE CONTAINER_ID:/books/
docker exec -it CONTAINER_ID chmod a+w /books/METADATA.DB.FILE
```
Verify
```bash
docker exec -it CONTAINER_ID ls -lah /books
```

Credit to [tikg's comment](https://github.com/linuxserver/docker-calibre-web/issues/30#issuecomment-1370898505) on the [linuxserver/docker-calibre-web](https://github.com/linuxserver/docker-calibre-web) repository and [@viniciuspaes](https://github.com/viniciuspaes) for pointing this out.