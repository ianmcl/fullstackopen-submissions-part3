# Part 3a Node.js and Express

## Exercises 3.1.-3.6.

**NB:** It's recommended to do all of the exercises from this part into a new dedicated git repository, and place your source code right at the root of the repository. Otherwise, you will run into problems in exercise 3.10.

**NB:** Because this is not a frontend project and we are not working with React, the application **is not created** with create vite@latest -- --template react. You initialize this project with the `npm init` command that was demonstrated earlier in this part of the material.

**Strong recommendation:** When you are working on backend code, always keep an eye on what's going on in the terminal that is running your application.

### 3.1: Phonebook backend step 1

Implement a Node application that returns a hardcoded list of phonebook entries from the address http://localhost:3001/api/persons.

Data:

```
    [
        {
          "id": 1,
          "name": "Arto Hellas",
          "number": "040-123456"
        },
        {
          "id": 2,
          "name": "Ada Lovelace",
          "number": "39-44-5323523"
        },
        {
          "id": 3,
          "name": "Dan Abramov",
          "number": "12-43-234345"
        },
        {
          "id": 4,
          "name": "Mary Poppendieck",
          "number": "39-23-6423122"
        }
    ]
```

Output in the browser after GET request:

![JSON data of 4 people in browser from api/persons](https://fullstackopen.com//static/a4879a92f2a8bd2e96c6d67fe3f34383/5a190/22e.png)

Notice that the forward slash in the route `api/persons` is not a special character, and is just like any other character in the string.

The application must be started with the command `npm start`.

The application must also offer an `npm run dev` command that will run the application and restart the server whenever changes are made and saved to a file in the source code.

### 3.2: Phonebook backend step 2

Implement a page at the address [http://localhost:3001/info](http://localhost:3001/info) that looks roughly like this:

![Screenshot for 3.2](https://fullstackopen.com//static/26383e4e706a7f89c140690121be2ea1/5a190/23x.png)

The page has to show the time that the request was received and how many entries are in the phonebook at the time of processing the request.

There can only be one response.send() statement in an Express app route. Once you send a response to the client using response.send(), the request-response cycle is complete and no further response can be sent.

To include a line space in the output, use `<br/>` tag, or wrap the statements in `<p>` tags.

### 3.3: Phonebook backend step 3

Implement the functionality for displaying the information for a single phonebook entry. The url for getting the data for a person with the id 5 should be [http://localhost:3001/api/persons/5](http://localhost:3001/api/persons/5)

If an entry for the given id is not found, the server has to respond with the appropriate status code.

### 3.4: Phonebook backend step 4

Implement functionality that makes it possible to delete a single phonebook entry by making an HTTP DELETE request to the unique URL of that phonebook entry.

Test that your functionality works with either Postman or the Visual Studio Code REST client.

### 3.5: Phonebook backend step 5

Expand the backend so that new phonebook entries can be added by making HTTP POST requests to the address [http://localhost:3001/api/persons](http://localhost:3001/api/persons).

Generate a new id for the phonebook entry with the [Math.random](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) function. Use a big enough range for your random values so that the likelihood of creating duplicate ids is small.

### 3.6: Phonebook backend step 6

Implement error handling for creating new entries. The request is not allowed to succeed, if:

- The name or number is missing
- The name already exists in the phonebook

Respond to requests like these with the appropriate status code, and also send back information that explains the reason for the error, e.g.:

```
{ error: 'name must be unique' }
```

# Part 3b Deploying app to internet

## Exercises 3.9.-3.11

The following exercises don't require many lines of code. They can however be challenging, because you must understand exactly what is happening and where, and the configurations must be just right.

### 3.9 Phonebook backend step 9

Make the backend work with the phonebook frontend from the exercises of the previous part. Do not implement the functionality for making changes to the phone numbers yet, that will be implemented in exercise 3.17.

You will probably have to do some small changes to the frontend, at least to the URLs for the backend. Remember to keep the developer console open in your browser. If some HTTP requests fail, you should check from the _Network_\-tab what is going on. Keep an eye on the backend's console as well. If you did not do the previous exercise, it is worth it to print the request data or `request.body` to the console in the event handler responsible for POST requests.

### 3.10 Phonebook backend step 10

Deploy the backend to the internet, for example to Fly.io or Render.

Test the deployed backend with a browser and Postman or VS Code REST client to ensure it works.

**PRO TIP:** When you deploy your application to Internet, it is worth it to at least in the beginning keep an eye on the logs of the application **AT ALL TIMES**.

Create a README.md at the root of your repository, and add a link to your online application to it.

**NOTE**: as it was said, you should deploy the BACKEND to the cloud service. If you are using Fly.io the commands should be run in the root directory of the backend (that is, in the same directory where the backend package.json is). In case of using Render, the backend must be in the root of your repository.

You shall NOT be deploying the frontend directly at any stage of this part. It is just backend repository that is deployed throughout the whole part, nothing else.

### 3.11 Full Stack Phonebook

Generate a production build of your frontend, and add it to the Internet application using the method introduced in this part.

**NB** If you use Render, make sure the directory `dist` is not ignored by git on the backend.

Also, make sure that the frontend still works locally (in development mode when started with command `npm run dev`).

If you have problems getting the app working make sure that your directory structure matches [the example app](https://github.com/fullstack-hy2020/part3-notes-backend/tree/part3-3).
