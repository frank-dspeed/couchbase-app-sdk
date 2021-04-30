# couchbase-app-sdk
A Collection of Components that turns your Couchbase Backend into a Firebase like Solution to build a Fullstack Application.

## Main Concepts
This is running on v8 Isolates directly on Every couchbase Node to reduce roundtrip Costs it uses The Couchbase Datacenter Protocol to run code
on the Correct Nodes where your data is.

## Realtime Data Subscriptions
Similar to superbase.

## Features
- Auth 
- Storage
- Functions
- hosting
- crash and Error reporting
- analytics
- ML
- push notifications
- remote config.

## Basic Deployment
- stealify/stealify (v8 isolates)
- couchbase cluster
- create system bucket for logging (traffic, and general node events) needs Access Level Administrator
- Create users and roles via the permission system
- For local dev consider a low ttl for most logging events so you do not put as much presure on your development machine
- git clone https://github.com/frank-dspeed/couchbase-app-sdk and build it with stealify or choose releases and download linux/64 binarys
- work with the cb-app-sdk or deploy the cb-app-ui via cb-app-sdk install ui command

## Internals
- nginx gets configured by v8 isolates that read the system bucket 
- primary data storage is ceph based while operational data is couchbase centric this allows realtime Analytics
- API's to kafka and solr as also elastic search are provided while not needed most of the time.
