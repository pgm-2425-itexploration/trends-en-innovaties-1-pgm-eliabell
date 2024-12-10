# Step-by-Step Guide to Create a NestJS Project

NestJS is a powerful, progressive Node.js framework for building scalable and maintainable server-side applications. Here's a quick guide to get you started:

---

## 1. **Install NestJS CLI**
The CLI simplifies project creation and development tasks.
```bash
npm i @nestjs/cli
```

This command installs the NestJS CLI globally on your system, allowing you to create and manage NestJS projects from any directory.

Verify the installation by checking the version:
```bash
npm nest --version
```

---

## 2. **Create a New Project**
Create a new NestJS project using the CLI. Most of the documentation just says that you need to do "nest new ..." but it will probabily say that you dont have it installed, thats why we use npx. 

once it asks you to choose what package manager, choose npm
```bash
npx nest new project-name
```

Navigate into the project directory:
```bash
cd project-name
```

---

## 3. **Run the Application**
Start the development server.
```bash
npm run start:dev
```

Open your browser and navigate to `http://localhost:3000` to see your application running. Since it wont give you the link inside of the terminal. 

---

## 4. **Create a Module**
Generate a new module.
```bash
npx nest generate module users
```

---

## 5. **Create a Controller**
Generate a new controller.
```bash
npx nest generate controller users
```

---

## 6. **Create a Service**
Generate a new service.
```bash
npx nest generate service users
```

---

## 7. **Define a Route**
Open the `users.controller.ts` file and define a route.
```typescript
import { Controller, Get } from '@nestjs/common';
import { UsersService } from './users.service';

@Controller('users')
export class UsersController {
  constructor(private readonly usersService: UsersService) {}

  @Get()
  findAll() {
    return this.usersService.findAll();
  }
}
```

---

## 8. **Implement the Service**
Open the `users.service.ts` file and implement the service.
```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class UsersService {
  private readonly users = [{ id: 1, name: 'John Doe' }];

  findAll() {
    return this.users;
  }
}
```

---

## 9. **Test the Application**
Run the application again.
```bash
npm run start:dev
```

Navigate to `http://localhost:3000/users` to see the list of users.

---


if you would like to display your users or any other made data, import your file 

```ts
import { x } from './path/to/your/file'
```

map and display it 



Congratulations! You have created a basic NestJS application with a module, controller, and service.