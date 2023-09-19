# Problem
composition fails with message:
```
[INCONSISTENT_INPUT_OBJECT_FIELD]: Input object field "scoopsWetFood" will not be added to "FoodInput" in the supergraph as it does not appear in all subgraphs: it is defined in subgraph "cat" but not in subgraphs "chicken", "cow", "dog" and "racoon".
```    
The message lists all subgraphs, even those without the type `FoodInput` so it makes it hard to know which subgraphs I need to look into. I would expect the message to be: 
```
[INCONSISTENT_INPUT_OBJECT_FIELD]: Input object field "scoopsWetFood" will not be added to "FoodInput" in the supergraph as it does not appear in all subgraphs: it is defined in subgraph "cat" but not in subgraphs "dog".
```  

```shell
➜  rover-testing git:(main) ✗ rover supergraph compose --config supergraph.json > supergraph.graphql 
⌛ resolving SDL for subgraphs defined in supergraph.json
🎶 composing supergraph with Federation v2.5.4
HINT: [INCONSISTENT_INPUT_OBJECT_FIELD]: Input object field "scoopsWetFood" will not be added to "FoodInput" in the supergraph as it does not appear in all subgraphs: it is defined in subgraph "cat" but not in subgraphs "chicken", "cow", "dog" and "racoon".

```
