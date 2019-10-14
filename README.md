### Changes in this fork

- removed binary from sources
- node v12.x support

# utmp

utmp parser for node.js

## Installation

```bash
npm install samplx-utmp
 ```

## Usage

### Example

```js
const UtmpParser = require('samplx-utmp');

const p = new UtmpParser('/var/log/wtmp');

p.on('data', function(d) {
  console.log("got record:", d);
})

p.run();

```

outputs something like...

```text
got record: { type: 'USER_PROCESS',
  pid: 54172,
  line: 'pts/0',
  id: 808416116,
  user: 'hellokitty',
  host: '10.0.1.11',
  exit_status: { termination: 0, code: 0 },
  session: 0,
  timestamp: Sat Sep 14 2013 07:02:06 GMT-0700 (PDT),
  address: 'a00:10b::' }
```

## TODO

* use ffi to read utmp definitions from libc.. don't hardcode them
