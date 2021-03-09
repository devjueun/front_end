# nodejs


## 노드 mong

0) 윈도우 노드js 
https://www.ucert.co.kr/wiki/w/%EC%9C%88%EB%8F%84%EC%9A%B0_node_js_%EC%84%A4%EC%B9%98#.ED.99.95.EC.9D.B8_.EC.82.AC.ED.95.AD  
2) 전체코드  
http://skilnote-for-react.co.kr/skilnote1/myshortcut/node-react-boiler-plate/2

2) 조치1
https://jootc.com/p/201912253249 #5000번 포트를 이미 사용중이라는 메시지를 읽고 사용중인 포트종료

3) 조치2
https://okky.kr/article/842446
https://edu.goorm.io/qna/11059 #혹시나 하는 마음에 들어가봤는데 역시나 mongodb database access에서 비번 설정 해주어야함

-------------------------------------------------------------------

## index.js


const express = require('express')
const app = express()
const port = 5000

const mongoose = require('mongoose')
mongoose.connect('mongodb+srv://이름:비밀번호@cluster0.secu6.mongodb.net/db네임?retryWrites=true&w=majority',{
    useNewUrlParser: true, useUnifiedTopology: true, useCreateIndex: true, useFindAndModify: false
}).then(() => console.log('MongoDB Connected...'))
  .catch(err => console.log(err))
  



------------------------------------------------------------------------------------------------------
app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:14364) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
events.js:292
      throw er; // Unhandled 'error' event
      ^

Error: listen EADDRINUSE: address already in use :::5000
    at Server.setupListenHandle [as _listen2] (net.js:1318:16)
    at listenInCluster (net.js:1366:12)
    at Server.listen (net.js:1452:7)
    at Function.listen (C:\Users\###\Desktop\node\boiler_plate\node_modules\express\lib\application.js:618:24)
    at Object.<anonymous> (C:\Users\###\Desktop\node\boiler_plate\index.js:17:5)
    at Module._compile (internal/modules/cjs/loader.js:1063:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1092:10) 
    at Module.load (internal/modules/cjs/loader.js:928:32)
    at Function.Module._load (internal/modules/cjs/loader.js:769:14)
    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:72:12)
    at internal/main/run_main_module.js:17:47
Emitted 'error' event on Server instance at:
    at emitErrorNT (net.js:1345:8)
    at processTicksAndRejections (internal/process/task_queues.js:80:21) {    
  code: 'EADDRINUSE',
  errno: -4091,
  syscall: 'listen',
  address: '::',
  port: 5000
}
npm ERR! code ELIFECYCLE
npm ERR! boiler_plate@1.0.0 start: `node index.js`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the boiler_plate@1.0.0 start script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\###\AppData\Roaming\npm-cache\_logs\2021-03-09T13_47_16_869Z-debug.log
PS C:\Users\###\Desktop\node\boiler_plate> ^C
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:18408) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at TLSSocket.ondata (internal/streams/readable.js:719:22)
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)? n
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:236) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at TLSSocket.ondata (internal/streams/readable.js:719:22)
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)? Y
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:17952) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at TLSSocket.ondata (internal/streams/readable.js:719:22)
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)? ny
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:6044) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\
    \Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at TLSSocket.ondata (internal/streams/readable.js:719:22)
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)? y
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:17104) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at MessageStream.Writable.write (internal/streams/writable.js:303:10)     
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)?
일괄 작업을 끝내시겠습니까 (Y/N)? y
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:4808) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
MongoError: bad auth : Authentication failed.
    at MessageStream.messageHandler (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\connection.js:268:20)
    at MessageStream.emit (events.js:315:20)
    at processIncomingData (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:144:12)
    at MessageStream._write (C:\Users\###\Desktop\node\boiler_plate\node_modules\mongodb\lib\cmap\message_stream.js:42:5)
    at writeOrBuffer (internal/streams/writable.js:358:12)
    at TLSSocket.ondata (internal/streams/readable.js:719:22)
    at TLSSocket.emit (events.js:315:20)
    at addChunk (internal/streams/readable.js:309:12)
    at readableAddChunk (internal/streams/readable.js:284:9)
    at TLSSocket.Readable.push (internal/streams/readable.js:223:10)
    at TLSWrap.onStreamRead (internal/stream_base_commons.js:188:23) {        
  ok: 0,
  code: 8000,
  codeName: 'AtlasError'
}
일괄 작업을 끝내시겠습니까 (Y/N)? y
PS C:\Users\###\Desktop\node\boiler_plate> npm run start

> boiler_plate@1.0.0 start C:\Users\###\Desktop\node\boiler_plate
> node index.js

(node:6596) Warning: Accessing non-existent property 'MongoError' of module exports inside circular dependency
(Use `node --trace-warnings ...` to show where the warning was created)       
Example app listening on port 5000
(node:6596) DeprecationWarning: Listening to events on the Db class has been deprecated and will be removed in the next major version.
MongoDB Connected...
