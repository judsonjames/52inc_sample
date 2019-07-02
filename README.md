# 52inc_sample

## Prerequisites
- docker
- docker-compose
- npm

## How to Run
1. The React application has been throwing 404's when using `serve` to supply the application, so I'm using
   the development server. Because of this we have to manually install the modules.
   ```bash
   cd react_frontend
   npm install
   cd ..
   ```
2. The Django/Nginx/Postgres are built off of my personal website docker chain, so they are tested and run accordingly.
3. To execute:
   ```
   docker-compose up --build
   ```
   Wait for the React application to go online before going to the designated URL. The development server takes a second.
4. When the development server for React goes online, you can proceed to the application at http://localhost:5252

## What the application does
- The application is a combination of a Django REST API and a React frontend. At http://localhost:5252, the user can see the
  the Todo app shown with React. The user can switch between 'complete' and 'incomplete' tasks, and each can be 
  updated manually.
- If the user travels to http://localhost:5252/backend/api/todos, they can POST to the database manually and refresh the
  React application manually to see the changes.
- The Django Admin page is also available at http://localhost:5252/backend/admin if they wish to create a superuser account
  in the Django container. This will provide an easier administration access.

## What could be improved
- Most importantly, the development server for React isn't a long term solution. There are times when I can build the
  application and use `serve` to deploy it, however, in testing I wasn't able to make it consistent. I'm not sure the
  reason.
- There is currently no way to identify a Todo list for a User, as such I'll need to research JWTs and see how they work
  such that Django User can be used to consolidate user information.
