FROM qmcgaw/latexdevcontainer:latest-full

RUN apt update
RUN apt install libfontconfig software-properties-common -y
RUN apt-add-repository contrib
RUN apt-add-repository non-free
RUN apt update
RUN apt install ttf-mscorefonts-installer unzip -y
