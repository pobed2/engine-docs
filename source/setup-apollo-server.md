---
title: Set up Engine with Apollo Server
sidebar_title: Node with Apollo Server
description: Get Engine running with Apollo Server.
---

With just a few minutes of setup, you can supercharge Apollo Server with Apollo Engine to get performance tracing and error tracking. Let's get started!

<h2 id="setup-guide">Setup guide for Apollo Server</h2>

To get Engine running with Apollo Server, just follow these three steps.

<h3 id="api-key" title="Get API key">1. Get an Engine API key</h3>

[Log into Apollo Engine](http://engine.apollographql.com/) via your browser and create a service to get an API key. We'll pass it into our Apollo Server constructor in the next step.

<h3 id="apollo-engine" title="Add Engine">2. Add the Engine API to the node environment</h3>

The API key can be passed directly to the Apollo Server constructor.

```js lines=6-8
const { ApolloServer } = require('apollo-server');

const server = new ApolloSever({
  typeDefs,
  resolvers,
  engine: {
    apiKey: 'YOUR API KEY HERE',
  },
});

server.listen().then(({ url }) => {
  console.log(`🚀  Server ready at ${url}`);
});
```

And you're done!

Reporting can also be enabled by setting the `ENGINE_API_KEY` environment variable to your API key. This can be done during the invocation of Apollo Server `ENGINE_API_KEY='YOUR API KEY' node index.js` or in a .env file using the [`dotenv` package](https://github.com/motdotla/dotenv#dotenv).

<h3 id="using-engine" title="Using Engine">3. Use Engine</h3>

Once Apollo Server is set up, navigate to the newly created Engine service in the [Engine UI](https://engine.apollographql.com). It should indicate that you've set everything up successfully. Start sending requests to your Node server to see performance metrics!

To get the most out of Engine, check out the documentation in the "Features" section on the left.

<h2 id="deploy" title="Deploy">Deploy</h2>

Now that we have integrated Engine into Apollo Server, we are ready to deploy Apollo Server on one of these cloud platforms:

- [Heroku](./deploy-heroku.html)
- [Now](./deploy-now.html)
