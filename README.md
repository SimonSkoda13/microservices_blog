# Microservices Blog Application

This project is a microservices-based blog application. It consists of several services that handle different parts of the application, such as posts, comments, moderation, and more. The services communicate with each other through an event bus.

## Services

- **Client**: The front-end React application.
- **Posts**: Handles creating and retrieving posts.
- **Comments**: Handles creating and retrieving comments for posts.
- **Moderation**: Moderates comments based on specific criteria.
- **Query**: Aggregates data from other services and provides it to the client.
- **Event Bus**: Manages events and ensures all services are synchronized.

## Prerequisites

- Docker
- Kubernetes
- Skaffold

## Setup

3. **Start Kubernetes cluster**:
   Ensure you have a Kubernetes cluster running. You can use Minikube or any other Kubernetes provider.

4. **Deploy Nginx Ingress Controller**:

   ```sh
   kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
   ```

5. **Deploy the application using Skaffold**:

   ```sh
   skaffold dev
   ```

6. **Access the application**:
   Add the following entry to your [hosts](http://_vscodecontentref_/0) file:
   ```
   127.0.0.1 posts.com
   ```
   Open your browser and navigate to `http://posts.com`.

## Project Structure

- **client**: Contains the React front-end application.
- **posts**: Contains the posts service.
- **comments**: Contains the comments service.
- **moderation**: Contains the moderation service.
- **query**: Contains the query service.
- **event-bus**: Contains the event bus service.
- **infra**: Contains Kubernetes deployment and service configuration files.

## Available Scripts

### Client

- `npm start`: Starts the React development server.
- `npm run build`: Builds the React application for production.

### Services

- `npm start`: Starts the service using Nodemon.

## License

This project is licensed under the MIT License.
