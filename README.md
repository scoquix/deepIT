# deepIT
Educational Project - Simple REST API (Spring, Hibernate, JPA, PostgreSQL)

API info: 

  Articles Endpoints:
  
    /api/articles/all   <- (GET) returns articles lists
    
    /api/articles/1   <- (GET) returns first article
    
    /api/articles/   <- (POST) insert article, send as JSON
    
    example:
        {
          "author_id":"12",
          "content":"New article", 
          "title":"New Title"
        }
        
    /api/articles/ <- (PUT) update article, put JSON in request body ( like above but with one extra field article_id)
    
    /api/articles?index=1 <- (DELETE) delete article with article_id = 1

    Requests POST, PUT and DELETE return HttpStatus, example: POST -> CREATED, PUT -> ACCEPTED, DELETE -> NO_CONTENT