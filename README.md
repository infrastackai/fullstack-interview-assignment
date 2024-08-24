# Fullstack Interview Assignment: Observer

## Project Overview

Build a fully functioning application to display telemetry data collected via OpenTelemetry SDKs. The application will feature a service map, service list, and detailed views for specific telemetry data.

## Step 1: Create an npm package

- Create a wrapper for OpenTelemetry SDKs named `infrastack-interview-fs-{your-initials}-{YYYYMMDD}`.
- Push the package to npm.
- Simplify the SDK configuration:

```javascript
import { register } from 'infrastack-interview-fs-{your-initials}-{YYYYMMDD}';

register({
    endpoint: "localhost:4317",
    instruments: ['http', 'express', 'mongodb'] // Add relevant instrumentations
});
```

**References:**
- [Next.js OpenTelemetry Example](https://replit.com/@infrastack-ai/NextJs-OpenTelemetry)
- [Express.js OpenTelemetry Example](https://github.com/infrastackai/otel/tree/main/examples/expressjs/basic-app)

## Step 2: Set up OpenTelemetry Collector

- Use Docker Compose to set up the OpenTelemetry Collector.
- Configure it to listen on gRPC port 4317.
- Provide a `docker-compose.yml` file in your project.

## Step 3: Configure ClickHouse Exporter

- Sign up for a free ClickHouse cloud instance.
- Configure the OpenTelemetry Collector to export data to ClickHouse.
- Include the exporter configuration in your `docker-compose.yml` file.

**Reference:** [ClickHouse Exporter README](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/exporter/clickhouseexporter/README.md)

## Step 4: Validate Data Streaming

- Create a simple script to verify that data is being correctly sent from your application to ClickHouse.
- Include this script in your project repository.

## Step 5: Create Multiple Sample Applications

- Develop at least three sample microservices with dummy endpoints.
- Implement inter-service communication to simulate a real-world scenario.
- Use your npm package to instrument these services.

## Step 6: Build the Dashboard

- Create a Next.js application for the dashboard.
- Implement a service map using React Flow:
  - Display services as nodes.
  - Show connections between services.
  - Indicate connection status (red/green) and latency on the edges.
- Create a service list view with key metrics.
- Implement a detailed view for each service showing traces and metrics.

## Step 7: Integrate AI-powered Assistant

- Use Vercel AI SDK to create a chat interface in the dashboard.
- Implement basic queries such as:
  - "Which endpoints are failing?"
  - "Why is service X experiencing high latency?"
- Ensure the AI can access and interpret the telemetry data from ClickHouse.

## Bonus: Implement Agentic Workflow

- Use CrewAI or a similar framework to create an agentic workflow.
- Implement a more complex scenario, such as automated root cause analysis or performance optimization suggestions.

## Technologies

- React and Next.js for the frontend
- OpenTelemetry Collector and JavaScript SDKs
- ClickHouse for data storage
- React Flow for service map visualization
- Vercel AI SDK for the AI assistant
- CrewAI (optional) for agentic workflows
- Docker and Docker Compose for containerization
- Tailwindcss

## Submission Guidelines

- Provide a GitHub repository with your complete project.
- Make sure to commit often with changes. Do not commit your solution at once! 
- Include a comprehensive README with setup instructions and any assumptions made.
- Dockerize the entire application for easy setup and evaluation.

## Evaluation Criteria

- Code quality and organization
- Proper use of TypeScript and React best practices
- Effective implementation of OpenTelemetry instrumentation
- Functionality and user experience of the dashboard
- Creativity in AI assistant implementation
- Bonus points for implementing the agentic workflow

Good luck with your assignment!