<img width="620" height="631" alt="Screenshot 2026-04-23 at 14 44 12" src="https://github.com/user-attachments/assets/33e02d76-aca2-4779-9954-2b65a7e59cfa" />
# Demo Websocket

[![Java](https://img.shields.io/badge/Java-21+-blue.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.0.5-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![React](https://img.shields.io/badge/React-19.2.5-blue.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-8.0.10-646CFF.svg)](https://vitejs.dev/)

A comprehensive demo application showcasing real-time WebSocket communication between a Spring Boot backend and a React frontend. This project demonstrates how to build a simple chat application using WebSockets, STOMP protocol, and modern web technologies.

## 📋 Project Summary

This is a full-stack WebSocket chat demo that illustrates the integration of Spring Boot's WebSocket support with a React-based frontend. The application allows multiple users to connect and exchange messages in real-time through WebSocket connections. It's designed as an educational example for developers learning about real-time web applications, WebSocket protocols, and full-stack development with Spring Boot and React.

The backend provides a RESTful API for basic operations and WebSocket endpoints for real-time messaging, while the frontend offers a clean, responsive chat interface built with React and Vite.

## ✨ Features

- **Real-time Messaging**: Instant message delivery using WebSocket connections
- **Multiple Transport Protocols**: Support for both WebSocket and SockJS fallback
- **STOMP Protocol**: Uses STOMP over WebSocket for message brokering
- **Responsive UI**: Modern React interface with CSS styling
- **Hot Module Replacement**: Fast development with Vite's HMR
- **Spring Boot Integration**: Leverages Spring's WebSocket and messaging support
- **Cross-Origin Support**: Configured for CORS to allow frontend-backend communication

## 📷 Screenshots

Below are sample screenshots of the running application. Place the attached image files into the `screenshots/` folder and update their names here if needed.

<img width="1512" height="982" alt="Screenshot 2026-04-23 at 14 28 02" src="https://github.com/user-attachments/assets/66799644-0cf2-4397-ac72-3c77681e706f" />

## 🏗️ Architecture

### Backend (Spring Boot)
- **WebSocket Configuration**: `WebSocketConfig.java` sets up STOMP endpoints and message brokers
- **Chat Controller**: `ChatController.java` handles WebSocket messages and broadcasts to subscribers
- **Message Model**: `Message.java` defines the structure of chat messages
- **Main Application**: `DemoWebsocketApplication.java` bootstraps the Spring Boot application

### Frontend (React + Vite)
- **App Component**: Main application container
- **Chat Component**: Handles WebSocket connections and message display
- **Message Components**: UI components for input and message lists
- **WebSocket Integration**: Uses `@stomp/stompjs` and `sockjs-client` for WebSocket communication

## 🛠️ Technologies Used

### Backend
- **Java 21**: Programming language
- **Spring Boot 4.0.5**: Framework for building the backend
- **Spring WebSocket**: WebSocket support
- **Spring Messaging**: STOMP protocol implementation
- **Maven**: Build and dependency management

### Frontend
- **React 19.2.5**: UI library
- **Vite 8.0.10**: Build tool and development server
- **@stomp/stompjs**: STOMP client for WebSocket communication
- **sockjs-client**: Fallback WebSocket library
- **ESLint**: Code linting

## 📋 Prerequisites

Before running this application, ensure you have the following installed:

- **Java 21 or higher**: Download from [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) or use your preferred JDK
- **Maven**: Usually comes with Java installations, or download from [maven.apache.org](https://maven.apache.org/download.cgi)
- **Node.js 18+**: Download from [nodejs.org](https://nodejs.org/)
- **npm**: Comes with Node.js installation

## 🚀 Installation and Setup

### Clone the Repository
```bash
git clone <repository-url>
cd Demo_Websocket
```

### Backend Setup
The backend uses Maven Wrapper, so no separate Maven installation is required.

### Frontend Setup
```bash
cd client
npm install
```

## ▶️ Running the Application

### Start the Backend
From the project root directory:

```bash
./mvnw spring-boot:run
```

The Spring Boot application will start on `http://localhost:8080`.

### Start the Frontend
In a separate terminal, from the `client` directory:

```bash
cd client
npm run dev
```

The Vite development server will start on `http://localhost:5173`.

### Access the Application
Open your browser and navigate to `http://localhost:5173` to use the chat application.

## 📡 API Documentation

### WebSocket Endpoints
- **Connect**: `/ws` - Main WebSocket endpoint
- **Subscribe**: `/topic/public` - Public chat messages
- **Send**: `/app/chat.sendMessage` - Send a message to the chat

### Message Format
```json
{
  "sender": "username",
  "content": "message content",
  "type": "CHAT"
}
```

## 🐛 Troubleshooting

### Frontend Native Binding Error
If you encounter errors related to missing native bindings (e.g., `@rolldown/binding-darwin-arm64`):

```bash
cd client
rm -rf node_modules package-lock.json
npm install
```

### Port Conflicts
If ports 8080 or 5173 are in use, you can change them:
- Backend: Modify `application.properties` or use `--server.port=8081`
- Frontend: Use `npm run dev -- --port 5174`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📚 Additional Resources

- [Spring WebSocket Documentation](https://docs.spring.io/spring-framework/docs/current/reference/html/web.html#websocket)
- [STOMP Protocol](https://stomp.github.io/)
- [React Documentation](https://react.dev/)
- [Vite Documentation](https://vitejs.dev/guide/)
