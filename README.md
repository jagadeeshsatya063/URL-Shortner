# URL Shortener

A simple URL shortener built using Node.js, Express.js, and MongoDB. This project allows users to generate shortened URLs, redirect to the original URLs, and track visit history with timestamps.

## Features
- Generate short URLs for long links
- Redirect users to the original URL
- Track visit history with timestamps

## Technologies Used
- Node.js
- Express.js
- MongoDB
- Mongoose

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/url-shortener.git
   cd url-shortener
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the root directory and add:
   ```
   MONGO_URI=your_mongodb_connection_string
   BASE_URL=http://localhost:5000
   ```

4. Start the server:
   ```bash
   npm start
   ```
   The server will run on `http://localhost:5000`

## API Endpoints

### 1. Shorten a URL
- **Endpoint:** `POST /api/shorten`
- **Body:**
  ```json
  {
    "longUrl": "https://example.com"
  }
  ```
- **Response:**
  ```json
  {
    "shortUrl": "http://localhost:5000/abc123"
  }
  ```

### 2. Redirect to Original URL
- **Endpoint:** `GET /:shortCode`
- **Response:** Redirects to the original URL.

### 3. Get URL Stats
- **Endpoint:** `GET /api/stats/:shortCode`
- **Response:**
  ```json
  {
    "originalUrl": "https://example.com",
    "shortUrl": "http://localhost:5000/abc123",
    "visitCount": 5,
    "visitHistory": ["timestamp1", "timestamp2"]
  }
  ```

## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

## License
This project is licensed under the MIT License.
