# Click the Variables button, above, to create your own variables.
GET ${exampleVariable1} // _search
{
  "query": {
    "${exampleVariable2}": {} // match_all
  }
}


GET /_search
{
  "query": {
    "match_all": {} 
  }
}



# Search by matching

GET /jsonplaceholder_todos/_search
{
  "query": {
    "match" : {"title": "aut"}
  }
}

# Create Alias

POST _aliases
{
  "actions": [
    {
      "add": {
        "index": "jsonplaceholder_users",
        "alias": "users"
      }
    }
  ]
}


# Get All records
 
GET /jsonplaceholder_users/_search
{
  "query": {
    "match_all": {} // match_all
  }
} 

# Get one by _id

GET /jsonplaceholder_users/_doc/SWdBUo4B87KnM4kScLeH




# Search by matching by token on some fields 


GET /jsonplaceholder_users/_search
{
  "query": {
    "match" : {"name": {"query": "leanne"}}
  }
}


# Search by matching by token on any fields 

GET /jsonplaceholder_users/_search
{
  "query": {
    "query_string": {"query": "info end-to-end"}
  }
}


GET /jsonplaceholder_users/_search
{
  "query": {
    "query_string": {
      "query": "(Bartholomebury) OR (Lebsackbury)",
      "default_field": "address.city" 
    }
  }
}


GET /gares-voyageurs/_mapping


GET /gares-voyageurs/_mapping/field/position_geographique
  

POST /_reindex
{
  "source": {
    "index": "gares-de-voyageurs"
  },
  "dest": {
    "index": "gares-voyageurs"
  }
}

