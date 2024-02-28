# QUICK DATA SERVER FOR TESTING

Just place database as json-file in a public Github resporitory.


To use with:  
[My JSON Server from typicode.com](https://my-json-server.typicode.com/) 

Call with:  
[https://my-json-server.typicode.com/Lakro/dtest](https://my-json-server.typicode.com/Lakro/dtest)



## LIMITS OPEN SOURCE (for free use)

+ 10KB db.json max
+ 5 max REST endpoints
+ 30 max items per endpoint 
+ all Servers public 
+ Requests are cached (1 minute)



## API

Source this information: 
[Typico JSON Server to self install](https://github.com/typicode/json-server/tree/main)

### Routes

Based on the example `db.json`, you'll get the following routes:

```
GET    /posts
GET    /posts/:id
POST   /posts
PUT    /posts/:id
PATCH  /posts/:id
DELETE /posts/:id

# Same for comments
```

```
GET   /profile
PUT   /profile
PATCH /profile
```

### PARAMS 


#### Conditions

- ` ` → `==`
- `lt` → `<`
- `lte` → `<=`
- `gt` → `>`
- `gte` → `>=`
- `ne` → `!=`

```
GET /posts?views_gt=9000
```

#### Range

- `start`
- `end`
- `limit`

```
GET /posts?_start=10&_end=20
GET /posts?_start=10&_limit=10
```

#### Paginate

- `page`
- `per_page` (default = 10)

```
GET /posts?_page=1&_per_page=25
```

#### Sort

- `_sort=f1,f2`

```
GET /posts?_sort=id,-views
```

#### Nested and array fields

- `x.y.z...`
- `x.y.z[i]...`

```
GET /foo?a.b=bar
GET /foo?x.y_lt=100
GET /foo?arr[0]=bar
```

#### Embed

```
GET /posts?_embed=comments
GET /comments?_embed=post
```

#### Delete

```
DELETE /posts/1
DELETE /posts/1?_dependent=comments
```




