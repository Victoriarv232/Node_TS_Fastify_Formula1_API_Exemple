# Formula 1 API

This is a minimal REST API built with Fastify and TypeScript, providing basic data about Formula 1 teams and drivers.

This project consists in a study, so the informations might not be complete.

## Project Setup

This project uses modern tooling for development and build processes:

* **Fastify** for fast and low-overhead HTTP server
* **TypeScript** for type safety and maintainability
* **Tsup** for bundling
* **TSX** for running TypeScript files directly

## Scripts

Use the following commands defined in `package.json`:

```bash
# Install dependencies
npm install

# Start in development mode with .env support
npm run start:dev

# Start in watch mode (auto-reload on file changes)
npm run start:watch

# Build the project to /dist
npm run dist

# Start from the built code
npm run start:dist
```

## Available Endpoints

### Get All Teams

Returns a list of all registered Formula 1 teams.

* **URL**

  ```
  GET /teams
  ```

* **Sample Response**

  ```json
  {
    "teams": [
      { "id": 1, "name": "McLaren", "base": "Woking, UK" },
      { "id": 2, "name": "Mercedes", "base": "Brackley, UK" },
      { "id": 3, "name": "Red Bull Racing", "base": "Milton Keynes, UK" }
    ]
  }
  ```

---

### Get All Drivers

Returns a list of all registered Formula 1 drivers.

* **URL**

  ```
  GET /drivers
  ```

* **Sample Response**

  ```json
  {
    "drivers": [
      { "id": 1, "name": "Max Verstappen", "team": "Red Bull Racing" },
      { "id": 2, "name": "Lewis Hamilton", "team": "Ferrari" },
      { "id": 3, "name": "Lando Norris", "team": "McLaren" }
    ]
  }
  ```

---

### Get Driver by ID

Returns the data of a specific driver by ID.

* **URL**

  ```
  GET /drivers/:id
  ```

* **URL Exemple**

  ```
  http://localhost:3333/drivers/1
  ```

* **URL Parameter**

  * `id` (string) - Driver ID

* **Sample Success Response**

  ```json
  {
    "driver": { "id": 1, "name": "Max Verstappen", "team": "Red Bull Racing" }
  }
  ```

* **Sample Not Found Response**

  ```json
  {
    "message": "Driver Not Found"
  }
  ```

---

## Server Configuration

* CORS is enabled for all origins using `@fastify/cors`
* The server runs on port **3333**
* Entry file: `src/server.ts`

## Technologies Used

* **Fastify** `^5.4.0`
* **TypeScript** `^5.4.3`
* **TSX** `^4.7.1`
* **Tsup** `^8.0.2`
* **@fastify/cors** `^11.1.0`


---

