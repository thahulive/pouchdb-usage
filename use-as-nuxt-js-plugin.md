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
import Vuex from 'vuex'

let pouchdb = new PouchDB('movies')
Vue.prototype.pouchdb = pouchdb

// use inside vuex store
Vuex.Store.prototype.pouchdb = pouchdb

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
