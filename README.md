# fast-api-project

This projects creates an social media style API with the FastAPI framework and Python. The Youtube tutorial is on FreeCodeCamp's channel, video [here](<https://youtu.be/0sOvCWFmrtA?si=81zxPiORHVsDrPFF>).

Fast API is designed for API development and allows auto documentation.

This will have a fully functional API with:

- Authentication
- CRUD operations
- Schema validation
- Documentation
- API testing

This application can be deployed into a Cloud provider. Tech stack:

- FastAPI
- Python
- PostGreSQL
- SQL Alchemy

Functionality:

- Create posts
- Like posts
- Update posts
- User specific tasks (creating users, logging in, voting on posts)


### Postgres table in SQL but the ORM takes care of this for us
```
CREATE TABLE public.posts
(
    id serial,
    title character varying NOT NULL,
    content character varying NOT NULL,
    published boolean NOT NULL DEFAULT True,
    created_at timestamp with time zone NOT NULL DEFAULT now(),
    PRIMARY KEY (id)
);

ALTER TABLE IF EXISTS public.posts
    OWNER to postgres;
```

### JWT Token Authentiation
1. `/login`, user provides email and password
2. Ensure the provided information is correct
3. Generate a JWT token and send back in payload
4. User accesses `/posts`, providing the JWT in the header
5. API verifies the token is valid and returns the data requested