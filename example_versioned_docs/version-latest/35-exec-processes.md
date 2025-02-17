---
title: Exec processes
id: exec-processed
slug: /exec-processed
sidebar_label: 35. Exec processes
description: Exec'ing Processes
keywords: [Wing language, HTTP]
image: /img/wing-by-example.png
---

```js playground example title="main.w"
bring util;

let output = util.exec("echo", ["-n", "Hello, Wing!"]);

// exec with custom environment variables
let output2 = util.exec("bash", ["--norc", "--noprofile", "-c", "echo $WING_TARGET $ENV_VAR"], { env: { ENV_VAR: "Wing" } });

// exec with inherited environment variables
let output3 = util.exec("bash", ["--norc", "--noprofile", "-c", "echo $WING_TARGET $ENV_VAR"], { inheritEnv: true });

// exec with current working directory
let output4 = util.exec("bash", ["--norc", "--noprofile", "-c", "echo Hello"], { cwd: "/tmp" });

log(output);
log(output2);
log(output3);
log(output4);
```

```bash title="Wing console output"
# Run locally with wing console
Hello, Wing!
Wing
sim
Hello
```


