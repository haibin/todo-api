# todo-api

```bash
$ rails new . --api
$ rails g scaffold todo title completed_at:timestamp
$ rails db:migrate
$ rails s
```

Create a todo.

```bash
$ curl -H "Content-Type:application/json" -X POST -d '{"todo":{"title": "Write a book"}}' http://localhost:3000/todos
{"id":1,"title":"Write a book","completed_at":null}
```

List all todo's.

```bash
$ curl http://localhost:3000/todos
[{"id":1,"title":"Write a book","completed_at":null}]
```

Pagination

```bash
$ curl http://localhost:3000/todos
{
    "data":[
        {
            "id":"1",
            "type":"todos",
            "attributes":{"title":"Write a book","completed-at":null}
        }
    ],
    "links":{
        "self":"http://localhost:3000/todos?page%5Bnumber%5D=1\u0026page%5Bsize%5D=25",
        "first":"http://localhost:3000/todos?page%5Bnumber%5D=1\u0026page%5Bsize%5D=25",
        "prev":null,
        "next":null,
        "last":"http://localhost:3000/todos?page%5Bnumber%5D=1\u0026page%5Bsize%5D=25"
    }
}
```

```bash
$ curl –-globoff http://localhost:3000/todos?page[size]=1&page[number]=2
```

# JSON API

https://jsonapi.org/
https://jsonapi.org/implementations/