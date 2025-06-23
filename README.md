# Tiny Reverse Proxy

`tinyrp` is a simple reverse proxy that forwards all incoming requests on a given port to a target backend URL. It is designed to be lightweight and easy to use, making it ideal for quick setups or development environments.

## Installation

```bash
go install github.com/davlgd/tinyrp@latest
```

## Usage

Set the required environment variables and run:

```bash
export REDIRECT_TO=https://www.example.com
export PORT=4242  # Optional, defaults to 8080
tinyrp
```

## Environment Variables

- `REDIRECT_TO` (required): Target URL to redirect requests to
- `PORT` (optional): Port to listen on (defaults to 8080)

## Examples

```bash
# Proxy to example.com on default port
REDIRECT_TO=https://www.example.com tinyrp

# Proxy to local service on custom port
REDIRECT_TO=http://localhost:3000 PORT=9090 tinyrp
```

## Features

- Forwards all HTTP methods (GET, POST, PUT, DELETE, etc.)
- Preserves headers, query parameters, and request body
- Automatically sets correct Host header for target domain
- Adds standard forwarding headers (X-Forwarded-Host, X-Real-IP)

It doesn't handle WebSocket, authentication, routing or advanced error handling and will never do: [KISS](https://en.wikipedia.org/wiki/KISS_principle).

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
