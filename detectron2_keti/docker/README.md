# Use the container (with docker ≥ 19.03)

```bash
cd docker/
# Build:
docker build --build-arg USER_ID=$UID -t detectron2:v0 .
# Launch (require GPUs):
docker run --gpus all -it \
  --shm-size=8gb --env="DISPLAY" --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
  --name=detectron2 detectron2:v0

# Grant docker access to host X server to show images
xhost +local:`docker inspect --format='{{ .Config.Hostname }}' detectron2`
```
