# idris2

1. podman build . -tag idris2

2. podman run -v "$PWD:$PWD":z -w "$PWD" idris2 -c Vect.idr

