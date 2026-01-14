# Quick AI - Full Stack AI SaaS Application

**Quick AI** is a full-stack AI-powered SaaS (Software as a Service) application built with the PERN stack (PostgreSQL, Express, React, Node.js). It features a suite of AI tools including content generation, image manipulation, and resume analysis, integrated with a subscription-based billing system.

## Features

- **AI Tools Suite:**
  - **Article Generator:** Generate full-length articles based on a topic and length.
  - **Blog Title Generator:** Create catchy titles for blogs based on keywords.
  - **Image Generator:** Text-to-image generation with selectable styles (3D, Anime, Realistic).
  - **Background Remover:** Remove backgrounds from uploaded images instantly.
  - **Object Remover:** Remove specific objects from images by describing them.
  - **Resume Analyzer:** AI analysis of resumes for strengths and improvements.
- **Community Showcase:** Public gallery to share and like AI-generated images.
- **SaaS Features:**
  - **Authentication:** Secure Sign-up/Login via Google or Email (Clerk).
  - **Credits System:** Free tier limits and Premium tier (unlimited) handling.
  - **Billing:** Integrated payment gateway.
- **Responsive Design:** Built with Tailwind CSS for mobile and desktop.

## Tech Stack

### Frontend
- **Framework:** React (Vite)
- **Styling:** Tailwind CSS
- **Routing:** React Router DOM
- **Icons:** Lucide React
- **HTTP Client:** Axios
- **Notifications:** React Hot Toast

### Backend
- **Runtime:** Node.js & Express.js
- **Database:** PostgreSQL (Neon Serverless)
- **File Storage:** Cloudinary
- **PDF Processing:** PDF-Parse

### AI & Services
- **Auth:** Clerk
- **Text AI:** Google Gemini API
- **Image AI:** ClipDrop API

## Environment Variables

Create `.env` files in the `client` and `server` folders respectively.

### Client (`client/.env`)
```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASE_URL=http://localhost:3000
```

### Server (`server/.env`)
```env
PORT=3000
DATABASE_URL=your_neon_postgres_connection_string
CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
GEMINI_API_KEY=your_google_gemini_api_key
CLIPDROP_API_KEY=your_clipdrop_api_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

## Database Schema

Run this SQL command in your Neon/PostgreSQL console to create the table:

```sql
CREATE TABLE creations (
  id SERIAL PRIMARY KEY,
  user_id TEXT NOT NULL,
  prompt TEXT NOT NULL,
  content TEXT NOT NULL,
  type TEXT NOT NULL,
  publish BOOLEAN DEFAULT FALSE,
  likes TEXT[] DEFAULT '{}',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);
```

## Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/quick-ai.git](https://github.com/your-username/quick-ai.git)
cd quick-ai
```

### 2. Frontend Setup
```bash
cd client
npm install
npm run dev
```

### 3. Backend Setup
```bash
cd server
npm install
npm run server
```

## Deployment

- **Frontend:** Deploy the `client` folder to Vercel/Netlify.
- **Backend:** Deploy the `server` folder to Vercel/Render.
- **Database:** Use Neon PostgreSQL.

## License

This project is open source and available under the [MIT License](LICENSE).
