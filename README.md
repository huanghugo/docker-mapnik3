# docker-mapnik3

## Supported tags and respective `Dockerfile` links

* [`3.0.5`, `latest` (v3.0.5/Dockerfile)](https://github.com/mapsquare/docker-mapnik3/tree/master/v3.0.5)
* [`3.0.4` (v3.0.4/Dockerfile)](https://github.com/mapsquare/docker-mapnik3/tree/master/v3.0.4)

## What is Mapnik ?
Mapnik is an open source toolkit for developing mapping applications and rendering maps. 
More informations on mapnik.org and [GitHub](https://github.com/mapnik/mapnik)

## Usage
If you have for example a node project
```Dockerfile
FROM mapsquare/mapnik3:3.0.5

# Install curl and nodejs with script
RUN apt-get update \
  && apt-get install -y curl \
  && curl -sL https://deb.nodesource.com/setup_0.12 | bash - \
  && apt-get install -y nodejs \
  && apt-get purge -y curl

# Making a work directory
WORKDIR /app

# Add your own node source files
ADD . .

# Install packages and dependancies
RUN npm install

CMD ["npm", "start"]

```