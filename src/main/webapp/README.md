12:16:43	<fotios>	first thing, can you configure bower to save its configs somewhere else?
12:16:50	<fotios>	maybe via an environment variable
12:17:07	<fotios>	your best bet would be to use $OPENSHIFT_DATA_DIR/.bower
"bower install --config.directory=$OPENSHIFT_HOMEDIR/.node_modules"
config: process.env.XDG_CONFIG_HOME, data: process.env.XDG_DATA_HOME, cache: process.env.XDG_CACHE_HOME
$OPENSHIFT_DATA_DIR/CREDENTIALS
http://logs.nodejs.org/openshift/2013-07-25


http://bower.io/docs/config/
https://github.com/bower/bower.json-spec
https://docs.google.com/document/d/17Nzv7onwsFYQU2ompvzNI9cCBczVHntWMiAn4zDip1w/edit#heading=h.oqro6l7qiz6u


To install client side components during npm install at the same time than server side libs, you can add in your package.json:

"dependencies": {
    ...
    "bower" : ""
},
"scripts": {
    ...
    "postinstall" : "node_modules/.bin/bower install"
}
