# pocketbase-docker

Docker image to run Pocketbase.

```shell
# default
docker run -p 8090:8090 \
    -v $(pwd)/pb_data/:/pocketbase/pb_data/ -v $(pwd)/pb_public/:/pocketbase/pb_public/ \
    ghcr.io/acifani/pocketbase:0.2.4-arm64

# custom host
docker run -p 8000:8000 \
    -v $(pwd)/pb_data/:/pocketbase/pb_data/ -v $(pwd)/pb_public/:/pocketbase/pb_public/ \
    ghcr.io/acifani/pocketbase:0.2.4-arm64 \
    serve --http 0.0.0.0:8000

# custom commands
docker run --rm \
    ghcr.io/acifani/pocketbase:0.2.4-arm64 \
    migrate
```
