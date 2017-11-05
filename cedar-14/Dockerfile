FROM heroku/cedar:14
MAINTAINER ademar

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF

RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots 5.4/main" > /etc/apt/sources.list.d/mono-xamarin.list \
    && apt-get update \
    && apt-get install -y --force-yes mono-devel ca-certificates-mono mono-vbnc \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get -q update
RUN apt-get -q -y --force-yes install curl gcc g++ make wget unzip git autoconf pkg-config libtool automake build-essential mono-devel gettext cmake

COPY build build
RUN chmod +x build
CMD ./build
