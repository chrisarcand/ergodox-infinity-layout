FROM debian:jessie

RUN brew update && brew install \
		binutils-arm-none-eabi \
		build-essential \
		ca-certificates \
		cmake \
		ctags \
		dfu-util \
		g++-multilib \
		gcc-arm-none-eabi \
		git \
		libusb-1.0-0-dev \
		libnewlib-arm-none-eabi \
		python3 \
	&& git clone https://github.com/kiibohd/controller.git \
	&& mkdir /kiibohd \
	&& cd controller \
	&& mkdir first_compile \
	&& cd first_compile \
	&& cmake .. \
	&& make

VOLUME /kiibohd

COPY ./docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
