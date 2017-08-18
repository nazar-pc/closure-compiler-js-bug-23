Reproducible example for https://github.com/google/closure-compiler-js/issues/23
```
npm install
node node_modules/.bin/google-closure-compiler-js source.js --compilationLevel ADVANCED_OPTIMIZATIONS --languageIn ECMASCRIPT5 --externs closure-externs.js --externs node-externs/util.js --externs node-externs/path.js --externs node-externs/fs.js --externs node-externs/events.js --externs node-externs/process.js --externs node-externs/https.js --externs node-externs/dgram.js --externs node-externs/string_decoder.js --externs node-externs/child_process.js --externs node-externs/net.js --externs node-externs/punycode.js --externs node-externs/core.js --externs node-externs/zlib.js --externs node-externs/vm.js --externs node-externs/stream.js --externs node-externs/tls.js --externs node-externs/readline.js --externs node-externs/http.js --externs node-externs/url.js --externs node-externs/dns.js --externs node-externs/repl.js --externs node-externs/cluster.js --externs node-externs/domain.js --externs node-externs/querystring.js --externs node-externs/crypto.js --externs node-externs/os.js --externs node-externs/tty.js --externs browser-externs/fileapi_synchronous.js
```

The interesting piece is in `closure-externs.js`, if you comment line with `var __read_sockaddr = function (addrp, addrlen) {};` it will stop crashing and eating enormous amounts of memory.
