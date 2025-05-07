# Reset Password Service

This is a standalone service for handling password reset functionality in the Sales Tracker application. It consists of a simple HTTP server that serves the password reset page and proxies requests to the main authentication service.

## Prerequisites

- Python 3.7+
- pip (Python package manager)

## Installation

1. Clone the repository
2. Navigate to the reset-password-app directory
3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

The server can be configured using the following environment variables:

- `PORT`: The port on which the server will run (default: 3000)
- `HOST`: The host address to bind to (default: 0.0.0.0)

## Running the Server

To start the server in development mode:

```bash
python serve_reset_password.py
```

The server will be available at `http://localhost:3000/reset-password.html`

## Production Deployment

For production deployment, you can use a WSGI server like Gunicorn:

```bash
gunicorn -b 0.0.0.0:$PORT serve_reset_password:make_app()
```

## API Endpoints

- `GET /reset-password.html`: Serves the password reset page
- `POST /auth/reset-password`: Proxies requests to the main authentication service

## Security Considerations

- Ensure the server is running over HTTPS in production
- Keep the server and its dependencies up to date
- Monitor the server for any suspicious activity
