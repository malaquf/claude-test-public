# Claude Test Public

A comprehensive testing repository for demonstrating various development practices and documentation standards.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [Testing](#testing)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [License](#license)
- [Support](#support)

## Overview

This repository serves as a centralized hub for testing and development practices. It combines documentation and examples that would typically be scattered across multiple repositories into a single, comprehensive resource.

## Features

- **Comprehensive Documentation**: Complete setup and usage instructions
- **Example Implementations**: Sample code and configuration files
- **Testing Framework**: Automated testing setup and examples
- **CI/CD Pipeline**: Continuous integration and deployment configurations
- **Security Guidelines**: Best practices for secure development
- **Performance Monitoring**: Tools and practices for performance tracking

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js (v14 or higher)
- npm or yarn
- Git
- Docker (optional, for containerized development)

### Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/security-approved/claude-test-public.git
   cd claude-test-public
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

## Installation

### Development Environment

For local development:

```bash
# Install dependencies
npm install

# Set up environment variables
cp .env.example .env

# Initialize the database
npm run db:migrate

# Start the development server
npm run dev
```

### Production Environment

For production deployment:

```bash
# Install production dependencies
npm ci --only=production

# Build the application
npm run build

# Start the production server
npm run start
```

## Usage

### Basic Usage

```javascript
const claudeTest = require('claude-test-public');

// Initialize the service
const service = new claudeTest.Service({
  apiKey: 'your-api-key',
  environment: 'development'
});

// Use the service
service.performAction()
  .then(result => console.log(result))
  .catch(error => console.error(error));
```

### Advanced Configuration

```javascript
const config = {
  database: {
    host: 'localhost',
    port: 5432,
    name: 'claude_test_db'
  },
  cache: {
    redis: {
      host: 'localhost',
      port: 6379
    }
  },
  security: {
    encryption: true,
    tokenExpiry: '24h'
  }
};
```

## API Documentation

### Authentication

All API requests require authentication via API key:

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
     https://api.claude-test.example.com/v1/endpoint
```

### Endpoints

#### GET /api/v1/status
Returns the current status of the service.

**Response:**
```json
{
  "status": "healthy",
  "version": "1.0.0",
  "timestamp": "2025-05-27T14:30:00Z"
}
```

#### POST /api/v1/process
Processes data according to specified parameters.

**Request:**
```json
{
  "data": "input data",
  "options": {
    "format": "json",
    "validate": true
  }
}
```

**Response:**
```json
{
  "id": "process-123",
  "status": "completed",
  "result": "processed data"
}
```

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Process

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes
4. Add tests for your changes
5. Run the test suite: `npm test`
6. Commit your changes: `git commit -am 'Add feature'`
7. Push to the branch: `git push origin feature-name`
8. Submit a pull request

### Code Style

- Use ESLint for JavaScript linting
- Follow the existing code style
- Write meaningful commit messages
- Include tests for new features

## Testing

### Running Tests

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode
npm run test:watch

# Run integration tests
npm run test:integration
```

### Test Structure

```
tests/
├── unit/           # Unit tests
├── integration/    # Integration tests
├── e2e/           # End-to-end tests
└── fixtures/      # Test data and fixtures
```

## Deployment

### Docker Deployment

```bash
# Build the Docker image
docker build -t claude-test-public .

# Run the container
docker run -p 3000:3000 claude-test-public
```

### Cloud Deployment

The application supports deployment to various cloud platforms:

- **AWS**: Use the provided CloudFormation templates
- **Google Cloud**: Deploy using Cloud Run
- **Azure**: Use Azure Container Instances
- **Heroku**: Direct deployment via Git

### Environment Variables

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `NODE_ENV` | Environment mode | Yes | `development` |
| `PORT` | Server port | No | `3000` |
| `DATABASE_URL` | Database connection string | Yes | - |
| `REDIS_URL` | Redis connection string | No | - |
| `API_KEY` | Service API key | Yes | - |

## Troubleshooting

### Common Issues

#### Connection Errors
- Check network connectivity
- Verify API credentials
- Ensure services are running

#### Performance Issues
- Monitor resource usage
- Check database connections
- Review log files

#### Authentication Problems
- Verify API key validity
- Check token expiration
- Review permission settings

### Debug Mode

Enable debug mode for detailed logging:

```bash
DEBUG=claude-test:* npm run dev
```

### Log Files

Logs are stored in:
- Development: `logs/development.log`
- Production: `logs/production.log`
- Error logs: `logs/error.log`

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

### Getting Help

- **Documentation**: Check this README and inline documentation
- **Issues**: Report bugs and feature requests via GitHub Issues
- **Discussions**: Join community discussions in GitHub Discussions
- **Email**: Contact the maintainers at support@claude-test.example.com

### Maintainers

- **Primary Maintainer**: [@security-approved](https://github.com/security-approved)
- **Contributors**: See [CONTRIBUTORS.md](CONTRIBUTORS.md)

### Changelog

See [CHANGELOG.md](CHANGELOG.md) for a detailed history of changes.

---

**Note**: This README consolidates documentation that was previously scattered across multiple repositories, providing a comprehensive guide for developers and users of the Claude Test Public project.