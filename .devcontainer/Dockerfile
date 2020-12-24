FROM haxe

#haxe stuff
RUN haxelib git heaps https://github.com/HeapsIO/heaps.git
RUN git clone https://github.com/HaxeFoundation/hashlink.git

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends build-essential libpng-dev libturbojpeg-dev libvorbis-dev libopenal-dev libsdl2-dev libmbedtls-dev libuv1-dev cmake
RUN cd hashlink && make all
RUN cd hashlink && make install
ENV PATH="/hashlink/:${PATH}"
RUN haxelib install hlopenal
RUN haxelib install hlsdl
RUN haxelib install hldx
