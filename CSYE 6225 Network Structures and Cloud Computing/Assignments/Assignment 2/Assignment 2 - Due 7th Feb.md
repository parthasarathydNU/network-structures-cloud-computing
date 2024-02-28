Check out [[01 Github Setup]]
[Assignment URL](https://spring2024.csye6225.cloud/assignments/02/)
### Issues present in last assignment : 
1. Project configuration - Issues in configuring typescript, typeorm, jest and tsoa to run on the same project
2. Missed covering test case where we have query params in the `healthz` end point
3. Jumped into advanced project configuration before understanding requirements of the task

### Overarching guidelines
1. The application is expected to automatically bootstrap the database at startup
2. All API request/response payloads should be in JSON - #assignment-2-testing should return 400 bad request if request payload has anything apart from a json
3. All API calls return proper HTTP status code #assignment-2-testing apart from status codes present in the first assignment, we have [authentication issues](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication) that might show up in this assignment show proper codes for that as well
4. #assignment-2-testing test cases for all other situations - perform test driven development, come up with test cases first
5. Only support token based authentication and not session based - #assignment-2-testing check if this can be disabled in any way - ask Prem
6. #assignment-2-testing readOnly data types should never be updated by an user. writeOnly data types should never be returned from the application

### API specific guidelines
1. Only support [token based Basic auth](https://security.stackexchange.com/questions/81756/session-authentication-vs-token-authentication) for authenticated end points
2. `password` should never be returned #assignment-2-testing 
3. I expect to use my email address as my username #assignment-2-testing verify if the username follows email format
4. #assignment-2-testing Application must return 400 Bad Request HTTP response code when a user account with the email address already exists.
5. Password is to be stored securely using the `BCrypt` password hashing scheme with a salt
6. #assignment-2-testing Update requests that have anything more than first name, last name and password need to return 400 bad request
7. #assignment-2-testing A user can only update their own account information
8. #assignment-2-testing users should be able to get their own information apart from pasword

### Tech stack
- nodejs runtime
- typecript - future looking
- TypeORM - interface with DB
- tsoa - API development
- jest - testing