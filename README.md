# DeepIT 
**Educational Project - Simple REST API (Spring, Hibernate, JPA, PostgreSQL)**
This backend version of the Spring DeepIT application only provides a REST API. There is no UI. The spring-deepit-angular project is a Angular front-end application that will consume the REST API.
***

## Public Articles Endpoints

  `/api/articles/all`   <- (GET) returns articles lists
  
  `/api/articles/1`   <- (GET) returns first article
  
  `/api/articles/`   <- (POST) insert article, send as JSON
  
     *example:*
        *{*
          *"author_id":"12",*
          *"content":"New article", *
          *"title":"New Title"*
        *}*
        
   `/api/articles/` <- (PUT) update article, put JSON in request body ( like above but with one extra field article_id)
   
   `/api/articles?index=1` <- (DELETE) delete article with article_id = 1
   
    **Requests POST, PUT and DELETE return HttpStatus, example: POST -> CREATED, PUT -> ACCEPTED, DELETE -> NO_CONTENT
    
## Security configuration ##
    ***
    In its default configuration, Deepit doesn't have authentication.
    Recently add Basic JWT Authorization.
    Security provides role separaion for specific endpoints:
    
    USER -> basic operations
    
    TEACHER -> basic operations + managing his own course
    
    MANAGER -> basic operations + administration
    
    Calling the url `/loginToken` (POST) you recieve a JWT Token to authorize yourself
    Without it, you will be deny at all urls, except `/api/article/*`, `loginToken', '/register'
