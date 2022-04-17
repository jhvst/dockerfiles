FROM alpine

RUN apk update
RUN apt add git
RUN git clone https://github.com/llvm/llvm-project.git
RUN mkdir llvm-project/build

WORKDIR llvm-project/llvm/projects
RUN git clone https://github.com/KhronosGroup/SPIRV-LLVM-Translator.git

WORKDIR llvm-project/build
RUN apk add cmake make clang binutils gcc musl-dev g++ python3
RUN cmake ../llvm -DLLVM_ENABLE_PROJECTS="clang"
RUN make llvm-spirv -j`nproc`

ENTRYPOINT [ "/llvm-project/build/bin/llvm-spirv" ]
CMD [ "--help" ]