# bashweb

Node api to write web servers using shell scripts

## Why?

Why not?

## Usage

Create a configuration file – I'll call it `config`.

Sample:
```bash
#!/bin/bash

# Import the bashweb API
bw=$(bashweb-api)

# Start listening
bw listen 3000
```

You can run a bashweb server with the command line:

```bash
bashweb ./config
```

Okay – pretty boring without routes, right?

Let's create a sample index route. I'll call it `index`

```bash
#!/bin/bash
bw=$(bashweb-api)

echo "<h1>Hey</h1>"
```

Now, let's add the route to our bashweb config:

```bash
#!/bin/bash

bw=$(bashweb-api)

bw get "/" "./index"

# Start listening
bw listen 3000
```

IMPORTANT: If you decide to import `bashweb-api` as something other than `bw`, *must* tell bashweb that, otherwise it will throw an error.

```bash
bashweb_api=$(bashweb-api)
bw path $bashweb_api
bw listen 3000
```