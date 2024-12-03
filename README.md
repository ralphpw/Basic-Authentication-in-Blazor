# Basic Authentication in Blazor

This example project demonstrates how to implement Basic Authentication in a Blazor Server application. The project is built on top of the standard .NET Blazor Server template and adds Basic Authentication security.

## Features

- Basic Authentication implementation
- Protected routes requiring authentication
- Simple hardcoded credentials (demo/demo123) for demonstration
- Client-side logout functionality
- Authentication state awareness in UI components

## Getting Started

### Prerequisites

- .NET 8.0 SDK or later
- An IDE (like Visual Studio) or code editor

### Running the Application

1. Clone the repository
2. Navigate to the project directory
3. Run the application:
```bash
dotnet run
```
4. Open a browser and navigate to `https://localhost:7076` or `http://localhost:5276`

### Login Credentials

For demonstration purposes, the following credentials are hardcoded:
- Username: `demo`
- Password: `demo123`

## Implementation Details

### Basic Authentication Handler

The authentication is implemented in `BasicAuthenticationHandler.cs`, which validates credentials against hardcoded values. In a production environment, this should be replaced with secure credential storage and validation.

### Protected Routes

Routes are protected using the `[Authorize]` attribute. Protected pages include:
- Weather forecast (`/weather`)
- Counter (`/counter`)

### Logout Implementation

The project includes a client-side logout mechanism. Due to the stateless nature of Basic Authentication, this implementation:
- Forces the browser to clear cached credentials
- Is client-side only (no server-side session termination)
- May require closing the browser for complete logout in some browsers

## Limitations

1. Basic Authentication sends credentials with every request
2. Credentials are only base64 encoded, not encrypted
3. No built-in mechanism for password reset or account management
4. Some browsers may cache credentials until the browser is closed

## Security Considerations

This implementation is for demonstration purposes only. For production use, consider:
- Using HTTPS exclusively
- Implementing proper credential storage and validation
- Using a more secure authentication method like JWT or Cookie Authentication
- Password hashing (if not HTTPS)

## Acknowledgments

Built on the standard .NET Blazor Server template with added Basic Authentication functionality.