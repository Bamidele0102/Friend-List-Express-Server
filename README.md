# Friend-List-Express-Server

This repository contains an application with API endpoints to perform Create, Retrieve, Update, and Delete operations on transient data using an Express server. It also provides authenticated access to the endpoints using JSON Web Tokens (JWT).

The application should allow you to add a friend with the following details: First name, Last name, Email and Date of birth. You will also be providing the application the ability to retrieve details, change details and delete the details.

## Objectives

- Create API endpoints to perform CRUD operations on transient data with an Express server.
- Implement authentication at the session level using JSON Web Tokens (JWT) for authorized access.

## Getting Started

### Clone the repository

```bash
git clone https://github.com/Bamidele0102/Friend-List-Express-Server.git
```

### Change into the directory

```bash
cd mxpfu-nodejsLabs
```

### Install the dependencies/packages

```bash
npm install
```

### Start the server without authentication

```bash
npm start
```

### Test the endpoints using cURL

```bash
curl localhost:5000/user/
```

#### GET by specific email

```bash
curl localhost:5000/user/johnsmith@gamil.com
```

#### Creating the POST method

To create a new user, use the following JSON data:

```json
{
    "firstName": "Jon",
    "lastName": "Lovato",
    "email": "jonlovato@theworld.com",
    "DOB": "10/10/1995"
}
```

```bash
curl --request POST 'localhost:5000/user?firstName=Jon&lastName=Lovato&email=jonlovato@theworld.com&DOB=10/10/1995'
```

To verify that the user has been created, use the `GET` method:

```bash
curl localhost:5000/user/jonlovato@theworld.com
```

#### Creating the PUT method

To update the `DOB` to `1/1/1971` for the user with the email `johnsmith@gamil.com`, use the following command:

```bash
curl --request PUT 'localhost:5000/user/johnsmith@gamil.com?DOB=1/1/1971'
```

To verify that the user has been updated, use the `GET` method:

```bash
curl localhost:5000/user/johnsmith@gamil.com
```

#### Creating the DELETE method

To delete the user with the email `johnsmith@gamil.com`, use the following command:

```bash
curl --request DELETE 'localhost:5000/user/johnsmith@gamil.com'
```

To verify that the user has been deleted, use the `GET` method.

### Start the server with authentication

```bash
npm run start-auth
```

### Test the endpoints using Postman

#### Login

Use the following JSON data in the body to login:

```json
{
    "user": {
        "name": "abc",
        "id": 1
    }
}
```

Send a `POST` request to:

```bash
POST http://localhost:5000/login
```

#### GET all users

```bash
GET http://localhost:5000/user
```

#### GET user by specific ID (email)

```bash
GET http://localhost:5000/user/johnsmith@gamil.com
```

#### POST request for a new user

Enter the following parameters in the body to create a new user:

- `firstName`: `Bob`
- `lastName`: `Smith`
- `email`: `bobsmith@gamil.com`
- `DOB`: `1/1/1978`

```bash
POST http://localhost:5000/user
```

Verify that the newly added values have been updated by doing a `GET` request.

#### PUT request

Enter the parameter(s) to be updated:

```bash
PUT http://localhost:5000/user/bobsmith@gamil.com
```

Verify that the newly added values have been updated by doing a `GET` request.

#### DELETE request

```bash
DELETE http://localhost:5000/user/bobsmith@gamil.com
```

Verify that the newly added values have been updated by doing a `GET` request.

## Contributing

Contributions are welcome! If you have any ideas, suggestions, or bug reports, please open an issue or submit a pull request.

## License

This project is licensed under the Apache License. See the [LICENSE](./LICENSE) file for more information.

## Contact

For any inquiries or support, please contact me via [mail](mailto:idowu.olayiwola.bamidele@gmail.com).
