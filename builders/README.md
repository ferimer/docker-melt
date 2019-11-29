These dockers prepares an image with all required dependencies to compile melt.

The building uses this script [1] but modified for adding support of openssl to ffmpeg in order to be possible to broadcast through Facebook (RTMPS)

Builded binaries will be available at exported VOLUME (/root/melt)

[1] https://raw.githubusercontent.com/mltframework/mlt-scripts/master/build/build-melt.sh

# Versions

There're two versions, buster and stretch based on these Debian flavours

# Run

See Makefile ;)
