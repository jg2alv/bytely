# bytely: URL shortener

bytely is a URL-shortening application built with Node.js, Express, and MongoDB. A browser interface submits destination URLs, creates short links, and provides clipboard feedback.

## 1. Features

- Create and persist short links.
- Generate identifiers using Adler-32 checksums and check for existing identifiers before insertion.
- Resolve stored identifiers through a browser redirect page.
- Render the interface with Mustache and serve static styles through Express.

## 2. Structure

`routes/index.js` maps requests to `controllers/URLController.js`. The Mongoose model in `models/URL.js` stores each destination and identifier. The `views` directory contains the submission and redirect pages.

## 3. Local configuration

The server reads `DATABASE` for its MongoDB connection and `PORT` for its listening port. The default port is 7777. The development entry point is `server.js`, exposed through the `dev` package script.

## 4. Current scope

This implementation focuses on link creation and resolution. Server-side URL validation, comprehensive error handling, and database-enforced identifier uniqueness remain areas for improvement.
