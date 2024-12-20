### ATL Transformation Server



This project is a REST API server designed to manage and execute ATL transformations. It integrates with the `atl_zoo` repository to access transformation definitions and provides endpoints to manage, search, apply, and chain transformations. 



#### Features

- Add, list, and delete ATL transformations. 
- Apply transformations using uploaded input models. 

- Chain multiple transformations. 
- Search within ATL transformation files.

#### API Endpoints

**List all transformations:**

```bash
curl localhost:8080/transformations
```

#### Get a Specific Transformation

```bash
curl localhost:8080/transformation/Class2Relational

```

#### Apply a Transformation

`Unique Metamodels (source & target)`

```bash
curl localhost:8080/transformation/Class2Relational/apply -F IN="@./Class.xmi        
```

`Multiple source Metamodels`

```bash
curl localhost:8080/transformation/Maven2Ant/apply \
  -F INMaven="@./example/mavenFile.xmi" \
  -F INProject="@./example/projectFile.xmi"

```

#### Search Transformations

```bash
curl localhost:8080/transformations/search?query=<search_term>
```

