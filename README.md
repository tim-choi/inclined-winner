# AI Support Chatbot

A full-stack AI-powered support chatbot application built with React and Express, powered by OpenAI's GPT models.

## Project Structure

```
inclined-winner/
├── backend/              # Express.js backend server
│   ├── server.js        # Main server file with API endpoints
│   ├── package.json     # Backend dependencies
│   └── .env.example     # Environment variables template
├── frontend/            # React frontend application
│   ├── src/
│   │   ├── App.js      # Main chat interface component
│   │   └── App.css     # Styles for the chat interface
│   ├── package.json    # Frontend dependencies
│   └── .env.example    # Frontend environment variables template
└── README.md           # This file
```

## Features

- 💬 Real-time chat interface with AI assistant
- 🎨 Modern, responsive UI design
- 📝 Conversation history support
- 🔄 Loading states and error handling
- 🧹 Clear chat functionality
- 🔒 Secure API key management with environment variables

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- OpenAI API key ([Get one here](https://platform.openai.com/api-keys))

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/tim-choi/inclined-winner.git
cd inclined-winner
```

### 2. Set up the Backend

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:

```bash
cp .env.example .env
```

Edit the `.env` file and add your OpenAI API key:

```
OPENAI_API_KEY=your_openai_api_key_here
PORT=5000
```

### 3. Set up the Frontend

```bash
cd ../frontend
npm install
```

(Optional) Create a `.env` file in the frontend directory if you want to change the API URL:

```bash
cp .env.example .env
```

## Running the Application

You need to run both the backend and frontend servers.

### Start the Backend Server

```bash
cd backend
npm start
```

The backend server will start on `http://localhost:5000`

### Start the Frontend Development Server

In a new terminal:

```bash
cd frontend
npm start
```

The frontend will start on `http://localhost:3000` and should automatically open in your browser.

## Usage

1. Open your browser and navigate to `http://localhost:3000`
2. Type your message in the input field at the bottom
3. Click "Send" or press Enter to send your message
4. The AI assistant will respond to your queries
5. Use the "Clear Chat" button to start a new conversation

## API Endpoints

### Backend API

- **GET** `/api/health` - Health check endpoint
  - Returns: `{ status: 'OK', message: 'AI Support Chatbot API is running' }`

- **POST** `/api/chat` - Send a message to the AI
  - Request body:
    ```json
    {
      "message": "Your message here",
      "conversationHistory": [
        { "role": "user", "content": "Previous message" },
        { "role": "assistant", "content": "Previous response" }
      ]
    }
    ```
  - Response:
    ```json
    {
      "reply": "AI response",
      "message": {
        "role": "assistant",
        "content": "AI response"
      }
    }
    ```

## Technologies Used

### Backend
- **Express.js** - Web server framework
- **OpenAI API** - AI language model
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment variable management

### Frontend
- **React** - UI library
- **Axios** - HTTP client
- **CSS3** - Styling

## Development

### Building for Production

#### Frontend
```bash
cd frontend
npm run build
```

This creates an optimized production build in the `frontend/build` directory.

#### Backend
The backend is production-ready as-is. Make sure to:
1. Set proper environment variables
2. Use a process manager like PM2 for production deployment
3. Set up proper logging and monitoring

## Troubleshooting

### Backend won't start
- Ensure you have created a `.env` file with a valid `OPENAI_API_KEY`
- Check if port 5000 is already in use
- Run `npm install` to ensure all dependencies are installed

### Frontend can't connect to backend
- Verify the backend server is running on port 5000
- Check the `REACT_APP_API_URL` in frontend `.env` file
- Ensure CORS is properly configured in the backend

### AI responses are slow
- This is normal - AI model inference can take a few seconds
- Check your internet connection
- Verify your OpenAI API key has sufficient credits

## Contributing

Feel free to submit issues and enhancement requests!

## License

ISC