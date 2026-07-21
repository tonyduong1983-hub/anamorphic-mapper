# Anamorphic Projection Mapper v2

Align source images to their projections and export pre-warped artwork for Photoshop.

## Features

- Load projection photo and source image
- Align source overlay on projection with keystone correction
- Define projection circle (gobo boundary)
- Draw masks to control light pass-through
- Export pre-warped PNG for use in Photoshop

## Quick Start

### Prerequisites

- Node.js >= 14.0.0
- npm

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Or start production server
npm start
```

The app will be available at `http://localhost:3000`

## Project Structure

```
anamorphic-mapper/
├── public/
│   ├── index.html          # Main UI
│   ├── css/
│   │   └── style.css       # Styles (optional)
│   └── js/
│       └── app.js          # Application logic
├── server.js               # Express server
├── package.json
├── .env
├── .gitignore
└── README.md
```

## Development

For development with auto-reload:

```bash
npm run dev
```

This uses `nodemon` to automatically restart the server when files change.

## Deployment

### Heroku

```bash
heroku create anamorphic-mapper
git push heroku main
heroku open
```

### Docker

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### Environment Variables

```env
PORT=3000
NODE_ENV=production
```

## API Endpoints

- `GET /` - Main application
- `GET /api/health` - Server health check

## Security

- JavaScript is served from the server (not exposed in HTML)
- CORS enabled for cross-origin requests
- Set appropriate environment variables for production

## License

MIT
