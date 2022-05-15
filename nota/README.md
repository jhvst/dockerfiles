# nota

1. `podman build . -t nota`

2. `podman run -v $PWD:/nota:z -w /nota nota build examples/index.nota`

This will create the `dist` folder with your HTML on the your current folder.

## `podman` and filesystem access

Podman may run into permission issues with the mounted folders. In these cases, one should run:

`podman unshare chown $whoami:$whoami -R $PWD`

where `$whoami` is the name of the user which runs the `podman` command.