==Web Service should describe itself (self explanatory) without documentation==

-> verbs are not allowed to use when create end point, not allowed to have two adjacent plural or singular words
`departments/it/employees/E001` -> this is the right way

-> Use HTTP method to represent the verb instead put verbs in the url
(actions are represents via HTTP methods)

`GET - find / query`
`POST - create`
`PUT - Replace or Create`
`PATCH = update`
`DELTE = Delete`