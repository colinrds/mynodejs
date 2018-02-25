# autocannon

fast HTTP/1.1 benchmarking tool written in Node.js

* guthub:  https://github.com/mcollina/autocannon

* Install
```
npm i autocannon -g
```

* Usage
```
Command Line
Usage: autocannon [opts] URL

URL is any valid http or https url.

Available options:

  -c/--connections NUM
        The number of concurrent connections to use. default: 10.
  -p/--pipelining NUM
        The number of pipelined requests to use. default: 1.
  -d/--duration SEC
        The number of seconds to run the autocannnon. default: 10.
  -a/--amount NUM
        The amount of requests to make before exiting the benchmark. If set, duration is ignored.
  -S/--socketPath
        A path to a Unix Domain Socket or a Windows Named Pipe. A URL is still required in order to send the correct Host header and path.
  -m/--method METHOD
        The http method to use. default: 'GET'.
  -t/--timeout NUM
        The number of seconds before timing out and resetting a connection. default: 10
  -T/--title TITLE
        The title to place in the results for identification.
  -b/--body BODY
        The body of the request.
  -i/--input FILE
        The body of the request.
  -H/--headers K=V
        The request headers.
  -B/--bailout NUM
        The number of failures before initiating a bailout.
  -M/--maxConnectionRequests NUM
        The max number of requests to make per connection to the server.
  -O/--maxOverallRequests NUM
        The max number of requests to make overall to the server.
  -r/--connectionRate NUM
        The max number of requests to make per second from an individual connection.
  -R/--overallRate NUM
        The max number of requests to make per second from an all connections.
        connection rate will take precedence if both are set.
        NOTE: if using rate limiting and a very large rate is entered which cannot be met,
              Autocannon will do as many requests as possible per second.
  -D/--reconnectRate NUM
        Some number of requests to make before resetting a connections connection to the
        server.
  -n/--no-progress
        Don't render the progress bar. default: false.
  -l/--latency
        Print all the latency data. default: false.
  -I/--idReplacement
        Enable replacement of [<id>] with a randomly generated ID within the request body. default: false.
  -j/--json
        Print the output as newline delimited json. This will cause the progress bar and results not to be rendered. default: false.
  -f/--forever
        Run the benchmark forever. Efficiently restarts the benchmark on completion. default: false.
  -v/--version
        Print the version number.
  -h/--help
        Print this menu.
```

* Programmatically
```
'use strict'

const autocannon = require('autocannon')

autocannon({
  url: 'http://localhost:3000',
  connections: 10, //default
  pipelining: 1, // default
  duration: 10 // default
}, console.log)
```

# node-ab

A command tool to test the performance of HTTP services.

* github: https://github.com/doubaokun/node-ab