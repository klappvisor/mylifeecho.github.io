---
layout: post
title: "Brainfuck script support for elasticsearch"
description: "" 
category: dev
tags: [ Scala, elasticsearch, Brainfuck ]
---
{% include JB/setup %}

This post is the continuation of the previous [Writing your own elasticsearch plugin in Scala assembled by Gradle step-by-step][hw-plugin] post. We are going to add the support of another scripting language to elasticsearch. When you have quite simple script to write, it's usually not a big deal to learn a new language on the sufficient level to make this script. But in case you have to write something more complex (you have to be careful with performance impact even with built in scripts) and efforts to learn ... you may want to use language you are good in.

and need two write some simple it will be [brainfuck][brainfuck]! Brainfuck interpreter [looks][brainfuck-int] quite simple in Scala, just 40 lines.

TODO: Script Module

```json
curl -XPOST localhost:9200/_search
{   "size": 0,
    "aggs": {
        "test": {
            "terms": {
                "script": "++++++++++[>+++++++>++++++++++>+++>+<<<<-]>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>+.",
                "lang" : "bf",
                "params": {}
            }
        }
    }
}
```

[hw-plugin]: 
[brainfuck-int]: http://peter-braun.org/2012/07/brainfuck-interpreter-in-40-lines-of-scala/
