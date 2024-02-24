FROM mono:latest
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get update \
  && apt-get install -y vim \
  && apt-get install -y nano \
  && apt-get install -y curl \
  && apt-get install -y htop \
  && apt-get install -y procps \
  && apt-get install -y findutils
RUN apt-get install git-core -y
RUN git clone --recursive https://github.com/fly-man-/WhiteCore-Dev.git
WORKDIR WhiteCore-Dev
RUN bash runprebuild.sh
RUN msbuild
ENTRYPOINT exec top -b