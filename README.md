# docker-data

A minimalistic docker data container that ONLY contains your data, nothing else.

Since the container does not have any binaries in it, and thus no valid ENTRYPOINT, you cannot *run* the container, only *create* it.

This container exposes a single volume, /data, where other containers can store their data. If you need other volumes, create your own data-container by modifying the Docker file in this repo or consider changing your other containers to use /data to store their data.

## Usage

	docker create --name my-container-data mattiash/data
	docker run --volumes-from my-container-data my-container
