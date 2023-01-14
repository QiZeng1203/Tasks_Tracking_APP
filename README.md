# Task Tracking App Project

This task tracking app involves both:
- an express server.js to host RESTFUL services and act as a static file server
- a create-react-app-based SPA build as static files that consume those services

## Setup

- Run `npm install`

## Notice for Windows users

Windows users will need to run `npm start-win`
- You can look at the differences in these package.json scripts
- There is a library (`cross-env`) that would resolve these differences

## Running for development

- In a terminal, run `npm start` to start the express server
- In a DIFFERENT terminal, run `npm run dev` to start the development CRA server
  - You need BOTH servers running for development
- Visit localhost on port **3000** (the development server port)
  - Service calls will be proxied by the development server to the express server
    - The browser only ever makes service calls to port 3000 (the port of the page)

## Running for production

- In a terminal, run `npm run build` to create the static files in the `build/` directory
- In a terminal, run `npm start` to start the express server
  - Only ONE server is running
- Visit localhost on port **4000** (the express server port)

## Home Page

- Since this is SPA application, it will make a fetch request `fetchSession()` to check whether the user is loggedin or not, if the user is loggedin, the user will see his/her tasks tracking content. if not, the user will be promoted to the Login page.

## Login Page
- A loggin form will allow user to enter only valid username to continue to see his/her tasks tracking content. an empty or no input for username, or a invalid username will cause error meesages to pop up at the top of the page.

## Content Page
- Loggedin user can see his/her tasks content, and the user can add/toggle/edit/delete a tasks. 
- When adding an task, if either of the date or the task title is null, the error message will pop up. If added successfully, the tasks item will automatically calculate the due days left for the task, or it will show "Past dues by N days" 
- When toggling an task, the task's status of complete will be switched, if an task is "completed", there is a line-through for that task to indicate.
- When editing an tasks, a new input box will be poped up to ask the user to change the task title/name. The user can confirm the change by clicking submit button or revoke the change by clicking cancel button. if the user didn't input a new name for the task item, the name will be revoked to the original one.
- When deleting an task, the specific task item will be deleted from the tracking system. if there is no more tasks left for a user, the user will see "No task yet, add one" alert.