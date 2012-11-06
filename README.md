# Cross-Data Center Replication (XDCR) Simulator in Sinatra

**When working**, can be used to "do stuff" with documents as they are streamed through XDCR to Sinatra. Still a work in progress...

# Pre-Requisites

```ruby
gem 'sinatra'
gem 'sinatra-basicauth'
gem 'json'
gem 'active_support' # for generating UUID's
```

# Usage

```bash
$ git clone git@github.com:scalabl3/xdcr-sinatra.git
$ cd xdcr-sinatra
$ ruby xdcr.rb
```

  1. In Couchbase Web Admin, click on XDCR Tab
  2. Click on Create Cluster Reference Button
  3. Create a name, and Add host and port (i.e. 127.0.0.1:4567)
  4. Enter your u: Administrator p: [your password]
  5. Click Done
  
#### Right now not everything is working for the Cluster Reference to work all the way through the Registration Process

# Couchbase Requests supported: #

**WORKING**

- /pools (GET)
- /pools/default (GET)
- /pools/default/buckets (GET)
- /pools/default/buckets/{bucket} (GET)
- /{database} (HEAD, GET)
- /{database}/{docid} (GET)

**NOT POSTING NEED TO CHECK**
- /{database}/_ensure_full_commit (POST)
- /{database}/_revs_diff (POST)
- /{database}/_bulk_docs (POST)

# Currently Working on... #

***Current Error***
This is for every vBucket number

2012-11-06 11:02:33 - Error replicating vbucket 955: 
{db_not_found, <<"http://Administrator:*****@127.0.0.1:4567/default/955;9e4d14d5a9be45cba5ec5534f42e129b/">>}