# Problem
The "listing" subgraph and the "product" subgraph are using federation-v1 schemas while the "review" subgraph is using
federation-v2 schema. The "review" schema is extending the Product entity but the compose step fails.

```shell
➜  rover-testing git:(main) ✗ rover supergraph compose --config supergraph.json > supergraph.graphql
composing supergraph with Federation v2.0.5.
error[E029]: Encountered 1 build error while trying to build a supergraph.

Caused by:
    UNKNOWN: [review] Field "Product.title" is marked @external but is not used in any federation directive (@key, @provides, @requires) or to satisfy an interface; the field declaration has no use and should be removed (or the field should not be @external).
    
        The subgraph schemas you provided are incompatible with each other. See https://www.apollographql.com/docs/federation/errors/ for more information on resolving build errors.

```
