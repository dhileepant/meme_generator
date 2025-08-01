# Meme Generator Application

## Overview
This is a full-stack meme generator application built with React, TypeScript, Node.js, Express, and MongoDB. It allows users to create, edit, share, and interact with memes.

## Prerequisites
- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas account)
- Cloudinary account (for image storage)
- OpenAI API key (optional, for AI-generated captions)

## Setup Instructions

### Backend Setup
1. Navigate to the backend directory:
   ```
   cd backend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file in the backend directory with the following variables (use .env.example as a template):
   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/meme_generator
   JWT_SECRET=your_jwt_secret_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   OPENAI_API_KEY=your_openai_api_key
   ```

4. Build the TypeScript code:
   ```
   npm run build
   ```

5. Start the backend server:
   ```
   npm run dev
   ```

### Frontend Setup
1. Navigate to the frontend directory:
   ```
   cd frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file in the frontend directory with the following variables:
   ```
   REACT_APP_API_URL=http://localhost:5000/api
   REACT_APP_CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   REACT_APP_CLOUDINARY_UPLOAD_PRESET=your_cloudinary_upload_preset
   ```

4. Start the frontend development server:
   ```
   npm start
   ```

## Running the Application
1. Make sure MongoDB is running on your local machine or you have a valid MongoDB Atlas connection string.
2. Start the backend server (from the backend directory): `npm run dev`
3. Start the frontend development server (from the frontend directory): `npm start`
4. Open your browser and navigate to `http://localhost:3000`

## API Endpoints

### Authentication
- `POST /api/users/register` - Register a new user
- `POST /api/users/login` - Login a user
- `GET /api/users/profile` - Get the current user's profile
- `GET /api/users/:username` - Get a user by username

### Memes
- `GET /api/memes` - Get all memes
- `GET /api/memes/:id` - Get a meme by ID
- `POST /api/memes` - Create a new meme
- `PUT /api/memes/:id` - Update a meme
- `DELETE /api/memes/:id` - Delete a meme
- `POST /api/memes/:id/like` - Like/unlike a meme
- `GET /api/memes/user/:username` - Get memes by a specific user
- `GET /api/memes/liked` - Get memes liked by the current user

### Comments
- `POST /api/memes/:id/comments` - Add a comment to a meme
- `DELETE /api/memes/:id/comments/:commentId` - Delete a comment

### AI Features
- `POST /api/ai/caption` - Generate a caption for a meme
- `GET /api/ai/idea` - Get a random meme idea

## Troubleshooting

### Common Issues

1. **MongoDB Connection Error**
   - Ensure MongoDB is running
   - Check your connection string in the `.env` file

2. **API Connection Issues**
   - Verify the backend server is running
   - Check that the `REACT_APP_API_URL` in the frontend `.env` file is correct

3. **Image Upload Problems**
   - Verify your Cloudinary credentials
   - Check the network tab in your browser's developer tools for specific errors

4. **Package Version Conflicts**
   - If you encounter dependency issues, try deleting the `node_modules` folder and `package-lock.json` file, then run `npm install` again