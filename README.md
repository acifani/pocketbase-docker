# pocketbase-docker

Docker image to run [PocketBase](https://pocketbase.io/). Images are available for linux amd64 and arm64.

## Usage

With plain docker

```shell
# default
docker run -p 8090:8090 \
    -v $(pwd)/pb_data/:/pocketbase/pb_data/ -v $(pwd)/pb_public/:/pocketbase/pb_public/ \
    ghcr.io/acifani/pocketbase:0.2.4-amd64

# custom host
docker run -p 8000:8000 \
    -v $(pwd)/pb_data/:/pocketbase/pb_data/ -v $(pwd)/pb_public/:/pocketbase/pb_public/ \
    ghcr.io/acifani/pocketbase:0.2.4-amd64 \
    serve --http 0.0.0.0:8000

# custom commands
docker run --rm \
    ghcr.io/acifani/pocketbase:0.2.4-amd64 \
    migrate
```

With docker compose

```yaml
version: '3.9'
services:
  pocketbase:
    image: 'ghcr.io/acifani/pocketbase:0.2-arm64'
    command: 'serve --http 0.0.0.0:8090'
    ports:
      - '8090:8090'
    volumes:
      - './pb_data:/pocketbase/pb_data'
      - './pb_public:/pocketbase/pb_public'
```
