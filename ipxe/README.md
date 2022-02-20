# ipxe

iPXE is the cool PXE loader

### How-to use

1. `podman run -it -v $(pwd):/mnt/coreos:Z .`
2. File called `undionly.kpxe` should appear in this folder. Copy it to the `tftp` folder. Then, continue with `tftp` install instructions.