headlands
=========

RESTified JCACHE / JSR-107

## Installation

1. Java 8 and Java EE 7 server. Tested with WildFly 8 and GlassFish v4
2. Download the [headlands.war](https://github.com/AdamBien/headlands/releases) and drop it into the "autodeployment" directory.

## Usage

### Create Cache

curl -i -XPUT -H"Content-type: application/json" -d'{"storeByValue":true}' http://localhost:8080/headlands/resources/caches/workshops

### Get cache names

curl http://localhost:8080/headlands/resources/caches/      

### Cache Configuration

curl -i -XOPTIONS http://localhost:8080/headlands/resources/caches/workshops  

### put('chief','duke') at the workshops cache

curl -i -XPUT -d'duke' http://localhost:8080/headlands/resources/caches/workshops/entries/chief

### List entries for the cache "workshops"

curl -i http://localhost:8080/headlands/resources/caches/workshops/entries/    

### Delete the entry with the key: "chief" at the cache workshops

curl -i -XDELETE http://localhost:8080/headlands/resources/caches/workshops/entries/chief      


### Delete all entries of the workshops cache

curl -i -XDELETE http://localhost:8080/headlands/resources/caches/workshops/entries      
