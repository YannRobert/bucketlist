bucketlist
==========

An Apache-like index for viewing the file and directory listing of an Amazon S3 bucket.

Demo: http://bucketlist-demo.s3-website-ap-southeast-2.amazonaws.com/

## About
``src`` contains the unminified source, and ``public`` contains the
latest (minified) build. When using Bucketlist, you can either go with
the "drop-in" solution and use ``index.html`` provided in the ``public``
folder, which has all of it's references to static assets pointing to a
Cloudfront CDN containing the latest release, or use ``src`` and host
the whole kit and kaboodle yourself.

## Prerequisites
* Edit your S3 bucket's permissions
  * Grant everyone permission to list
  * Add a rule to the CORS configuration to allow any origin to GET

## Configuration
Bucketlist is flexible - it can be used with any S3 bucket in any region,
with or without S3's static website hosting enabled. You can put the index
within the bucket itself, in another S3 bucket, or anywhere else you'd like.

### Hosted in the same S3 bucket
* Download either public/index.html or the contents of src/
* Update the ``title`` and the ``description`` tags in index.html
* Upload it to your bucket

### Hosted in another S3 bucket, or anywhere else
* Download either public/index.html or the contents of src/
* Update the ``title`` and the ``description`` tags in index.html
* Uncomment the ``url`` key in the ``window.bucketlistConfig`` object
  in index.html and change it to the URL of your S3 bucket
* Upload it to wherever you'd like to host it

## Options
Bucketlist takes 2 user configurable options in the form of the
``window.bucketlistConfig`` object, which can be found in the top of
index.html. To modify an option, simply uncomment it and change
it's value.

* url
  * The URL of the S3 bucket you'd like to generate a
    Bucketlist for
  * _Default_: the current ``window.location.host``
* limit
  * The number of results per page
  * _Default_: 100

## Credits
Bucketlist uses:
* [jQuery](https://github.com/jquery/jquery)
* [Bootstrap](https://github.com/twbs/bootstrap)
* [Sortable](https://github.com/HubSpot/sortable)

