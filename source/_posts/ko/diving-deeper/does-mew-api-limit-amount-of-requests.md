---
title: "Does MEW API Have a Limit on the Amount of Requests I Can Make?"
date: 2018-06-01 00:01:00
tags:
  - api
  - limit
  - requests
categories:
  - 
    - diving-deeper
primary_category: diving-deeper
primary_category_display_name: "Diving Deeper"
alias:
  - ko/diving-deeper/myetherapi-api-limits.html
---

# **Does MEW API Have a Limit on the Amount of Requests I Can Make?**

###### {% read_time title "Does MEW API Have a Limit on the Amount of Requests I Can Make?" %} min read

* * *

If you are a heavy user of our API or MyEtherWallet (MEW), you may get rate-limited.

## **If so, it typically looks something like this:**

<div class="scrollbox">
Error: Invalid JSON RPC response: ERROR: The request could not be satisfied. The origin closed the connection. Generated by cloudfront (CloudFront) Request ID: XXXXXXX \"
  at Object.InvalidResponse (/home/drone/projects/mew/asset-position-disposal/node_modules/web3/lib/web3/errors.js:38:16)
  at XMLHttpRequest.request.onreadystatechange (/home/drone/projects/mew/asset-position-disposal/node_modules/web3/lib/web3/httpprovider.js:115:32)
  at XMLHttpRequestEventTarget.dispatchEvent (/home/drone/projects/mew/asset-position-disposal/node_modules/xhr2/lib/xhr2.js:64:18)
  at XMLHttpRequest._setReadyState (/home/drone/projects/mew/asset-position-disposal/node_modules/xhr2/lib/xhr2.js:354:12)
  at XMLHttpRequest._onHttpResponseEnd (/home/drone/projects/mew/asset-position-disposal/node_modules/xhr2/lib/xhr2.js:509:12)
  at IncomingMessage.&lt;anonymous&gt; (/home/drone/projects/mew/asset-position-disposal/node_modules/xhr2/lib/xhr2.js:469:24)
  at emitNone (events.js:110:20)
  at IncomingMessage.emit (events.js:207:7)
  at endReadableNT (_stream_readable.js:1047:12)
  at _combinedTickCallback (internal/process/next_tick.js:102:11)
</div>

(<a href="https://ethereum.stackexchange.com/questions/24737/myetherwallet-json-rpc-interface-ratelimiting/25113#25113">Source</a>)

MyEtherWallet, at the time of this writing, rate-limits at 400 requests per minute (or about 6 requests per second). This is in order to prevent DDOS's like we have seen before, or people using our nodes to excess.

This should be more than enough for a single person's use, but feel free to reach out to us about why you need more, and we can adjust.

If you are going to be using it more than 400 req per minute on average, or just want to ensure uptime, we strongly recommend you get your own node.

Our backend infrastructure is on AWS and is open-source via Docker + CloudFormation walkthrough. You can actually do it yourself and run your own public or private node via [these instructions](https://github.com/MyEtherWallet/docker-geth-lb).

Or you could pay a small fee and use [QuikNode](https//quicknode.io/), which makes it even easier.

For both of these options, you could connect to your new node via the 'Add Custom Node' option in the network selector in the top-right corner. Further details on how to connect to your own node can be found [here](/@@@@@@/networks-and-nodes/unable-to-connect-to-custom-node/), or you could connect directly via API.
