# bpf docker for macOS

## build
docker build -t bpf-macos .

## run
docker run --it --rm \
    --privileged \
    -v /lib/modules:/lib/modules:ro \
    -v /etc/localtiime:/etc/localtime:ro \
    --pid=host \
    bpf-macos

command explain:
    -v : bind mount volume from host to container
    --privileged: allow container access to host device
    --rm : remove filesystem when the container exit.
