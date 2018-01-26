FROM node:9.4.0-alpine

ARG VCS_REF
ARG BUILD_DATE
ARG IMAGE_TAG_REF

# Metadata
LABEL maintainer="ralph.squillace@microsoft.com"
LABEL org.label-schema.vcs-ref=$VCS_REF \
      org.label-schema.name="Ratings Web App" \
      org.label-schema.description="Simple node web app" \
      org.label-schema.vcs-url="https://github.com/squillace/rating-web" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.docker.dockerfile="/Dockerfile"

ENV GIT_SHA $VCS_REF
ENV IMAGE_BUILD_DATE $BUILD_DATE
ENV IMAGE_TAG $IMAGE_TAG_REF

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8080

CMD [ "npm", "run", "container" ]