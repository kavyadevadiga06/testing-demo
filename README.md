# Hello World Mule Application

A simple Mule 4.x application that provides a "Hello World" REST API endpoint.

## Overview

This is a basic MuleSoft application that demonstrates:
- HTTP Listener configuration
- DataWeave transformation
- JSON response generation
- Basic logging

## Endpoints

### GET /helloworld
Returns a simple "Hello, World!" JSON response.

**Response:**
```json
{
  "message": "Hello, World!"
}
```

## Configuration

- **Port:** 8081 (configurable in config.properties)
- **Host:** 0.0.0.0 (configurable in config.properties)

## Running the Application

1. **Prerequisites:**
   - Java 17 or higher
   - Maven 3.6+
   - MuleSoft Runtime 4.11.2+

2. **Build the application:**
   ```bash
   mvn clean package
   ```

3. **Deploy to Mule Runtime:**
   - Copy the generated JAR file from `target/` directory to your Mule runtime's `apps/` folder
   - Or use the Mule Maven plugin for local testing

4. **Test the endpoint:**
   ```bash
   curl http://localhost:8081/helloworld
   ```

## Project Structure

```
helloworld-mule-app/
├── pom.xml                           # Maven configuration
├── src/main/
│   ├── mule/
│   │   ├── global.xml               # Global configurations
│   │   └── helloworld-mule-app.xml  # Main flow
│   └── resources/
│       └── config.properties        # Configuration properties
└── README.md
```

## Dependencies

- **Mule Runtime:** 4.11.2
- **HTTP Connector:** 1.11.1

## Configuration Properties

Edit `src/main/resources/config.properties` to customize:
- `http.host` - HTTP listener host (default: 0.0.0.0)
- `http.port` - HTTP listener port (default: 8081)

## Development

This application follows MuleSoft best practices:
- Configuration externalization using properties
- Separation of concerns (flows vs global configs)
- Proper error handling and logging
- Maven-based build process
