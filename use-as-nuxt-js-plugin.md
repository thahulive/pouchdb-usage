# Use PouchDB in Nuxt Js project

1. Install
------
```
npm install --save pouchdb
```

2. Config
------
* Create `pouchdb.js` file inside plugins directory  and copy paste this code
```
import Vue from 'vue';
import PouchDB from 'pouchdb';

let pouchdb = new PouchDB('movies')
Vue.prototype.pouchdb = pouchdb
Vue.prototype.$pouchdb = pouchdb.pouchdb

Vue.use(pouchdb);
```

* Link `pouchdb.js` to `nuxt.config.js` file
```
plugins: ['@/plugins/pouchdb']
```

2. Usage
------
```
this.pouchdb.allDocs({
    include_docs: true,
    attachments: true
}).then((movies)=>{
    console.log(movies)
})
```
