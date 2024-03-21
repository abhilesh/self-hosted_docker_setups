The [official nextcloud docker image](https://github.com/nextcloud/docker) does not come with [`ffmpeg`](https://ffmpeg.org/) pre-installed, which is required for media transcoding and generating previews. You can install `ffmpeg` by running the following command:

Replace CONTAINER_ID with the ID of the nextcloud container.

```bash
docker exec -it CONTAINER_ID apt-get update && apt-get install -y ffmpeg
```

However, this command would need to be re-run everytime we pull a new nextcloud image. To persistently install `ffmpeg`, we create a custom Dockerfile that extends the official nextcloud image and installs `ffmpeg` [(docker-compose-ffmpeg.yml)](./docker-compose-ffmpeg.yml):

To build the custom image, run:

```bash
docker compose build

docker compose up -d
```

To pull the latest nextcloud image for building the custom image, run:

```bash
docker compose build --pull

docker compose up -d
```

Some nextcloud workflows such as the [Automated media conversion](https://github.com/cwilby/nextcloud-workflow-media-converter?tab=readme-ov-file) run `ffmpeg` commands as a background process. If you are using such workflows, you may need to build the custom image for `cron` with `ffmpeg` installed.