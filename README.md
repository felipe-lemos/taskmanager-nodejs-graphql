# taskmanager-nodejs-graphql

Task Management API with NestJS and GraphQL

### **1. Project Context**

Develop a **Task Management API** using **NestJS and GraphQL**, ensuring authentication and best practices. The API will allow users to create accounts, manage their tasks, and view statistics about their activities.

### **2. Application Requirements**

✅ **Authentication and Authorization**

- Users can register and login.
- JWT will be used for authentication.
- Authorization middleware to protect private endpoints.

✅ **Task Management**

- Create, list, update and delete tasks.
- Categorize tasks (e.g., "Work", "Personal").
- Set task status (e.g., "Pending", "Completed").

✅ **Queries and Statistics**

- Return number of tasks by status and category.
- Advanced filters via GraphQL.

✅ **Best Practices and Security**

- Use of **DTOs and Validators** for input validation.
- **Modular architecture** and separation of concerns.
- **Documentation of technical decisions**.

### **3. Architectural Decisions**

🔹 **Choosing GraphQL over REST**

- Enables **flexible queries**, returning only necessary data.
- **Better performance** by avoiding multiple REST requests.

🔹 **NestJS as Framework**

- Modular architecture facilitates maintenance and scalability.
- Native GraphQL integration.

🔹 **Database and ORM**

- **PostgreSQL** + **Prisma ORM** (for ease of modeling and migrations).

🔹 **Authentication and Security**

- **JWT for authentication** (via Passport.js).
- **Guards and Middleware** to protect routes.
- **Rate limiting and CORS** enabled.

### **5. Implementation Example**

🔹 **GraphQL Schema (TypeDefs)**

```graphql
type Task {
  id: ID!
  title: String!
  description: String
  status: String!
  category: String!
  createdAt: String!
}

type Query {
  tasks: [Task]!
  task(id: ID!): Task
}

type Mutation {
  createTask(title: String!, description: String, category: String!): Task
  updateTask(id: ID!, status: String!): Task
  deleteTask(id: ID!): Boolean
}
```

### **6. Technologies Used**

- **NestJS** (Backend Framework)
- **GraphQL + Apollo Server** (API)
- **PostgreSQL + Prisma ORM** (Database)
- **Passport.js + JWT** (Authentication)
- **ESLint + Prettier** (Code Style)
