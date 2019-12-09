# piveau hub

**PREVIEW VERSION** 

piveau hub is an Open Data registry based on Semantic Web technologies    

## Installation

### Prerequisites
- Java JDK 11
- Node 10.15.0
- npm 6.4.1
- Docker and Docker Compose
- Maven

### Get the Code
```
$ git clone https://github.com/piveau-data/piveau-hub
$ git clone https://github.com/piveau-data/piveau-hub-registry
$ git clone https://github.com/piveau-data/piveau-hub-search
$ git clone https://github.com/piveau-data/piveau-hub-datastore
$ git clone https://github.com/piveau-data/piveau-hub-ui
```
### Build the Backend
```
$ cd piveau-hub-registry
$ mvn clean package -U -DskipTests
$ cd ..
$ cd piveau-hub-search
$ mvn clean package -U -DskipTests
$ cd ..
$ cd piveau-hub-datastore
$ mvn clean package -U -DskipTests
$ cd ..
```
### Build the Frontend
```
$ cd piveau-hub-ui
$ npm install
$ npm run build
```
### Init Elasticsearch
- Browse to `http://localhost:8082/shell.html`
- Execute `$ reset`

### Run it
```
$ docker-compose up --build
```

## Quick Manual

### Frontend
- The frontend is accessible via `http://localhost:8084`

### APIs
- SPARQL endpoint: `http://localhost:8890/sparql`
- Search endpoint: `http://localhost:8801`
- Registry endpoint: `http://localhost:8080`

### Create Test Data
- Test data can be found in "examples"
- Set the corrects headers when executing the HTTP request
- `Authorization:myapikey` `Content-Type:text/turtle` 

```
PUT localhost:8080/catalogues/catalog-1
```
```
PUT localhost:8080/datasets/dataset-1?catalogue=catalog-1
```