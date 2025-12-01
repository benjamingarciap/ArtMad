# ArtMad - Art Gallery Marketplace Platform

ArtMad is a full-stack web application that connects artists, galleries, and art buyers in Madrid. It's an art marketplace and discovery platform built with Node.js and Express.

## Features

## Tech Stack

### Backend

- **Node.js** with **Express.js**
- **MongoDB** with **Mongoose** ODM
- **Passport.js** for authentication (local strategy)
- **Express-session** with MongoDB session store
- **Bcrypt** for password hashing

### Frontend

- **Handlebars (HBS)** templating engine
- Vanilla JavaScript with API handlers
- Custom CSS styling

## Core Functionality

- **User Authentication** - Secure signup/login with Passport.js local strategy and bcrypt password hashing
- **Artwork Catalog** - Browse and discover artworks organized by genre
- **Advanced Search** - Search for artists, galleries, and artworks by name or genre
- **Profile Management** - Users can manage their content, artworks, and descriptions
- **Gallery/Artist Pages** - Detailed pages with portfolios and artwork collections
- **Interactive Maps** - Google Maps integration to display gallery locations
- **Image Upload** - Cloudinary integration for storing and serving artwork images

### User Roles

- **Artists** - Create profiles, upload artworks with images, and showcase portfolios
- **Galleries** - Curate collections, represent artists, and display locations on interactive maps

### Art Genres Supported

- Pintura (Painting)
- Escultura (Sculpture)
- Fotografía (Photography)
- Instalación (Installation)

### Integrations

- **Cloudinary** - Image hosting and management
- **Google Maps API** - Location visualization
- **Multer** - File upload handling

## Installation

1. Clone the repository:

```bash
git clone https://github.com/benjamingarciap/ArtMad.git
cd ArtMad
```

2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:

```
DB=your_mongodb_connection_string
GOOGLEKEY=your_google_maps_api_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

4. Run the application:

```bash
npm start
# or for development with nodemon
npm run dev
```

5. Open your browser and navigate to `http://localhost:3000`

## Project Structure

```
├── app.js                 # Main application configuration
├── models/
│   ├── user.js           # User model (artists & galleries)
│   └── artwork.js        # Artwork model
├── routes/
│   ├── index.routes.js   # Home and search routes
│   ├── authentication.routes.js
│   ├── artists.routes.js
│   ├── galleries.routes.js
│   ├── artworks.routes.js
│   └── api.routes.js     # API endpoints
├── views/                # Handlebars templates
├── public/
│   ├── javascripts/      # Client-side JavaScript
│   └── stylesheets/      # CSS files
└── config/
    └── cloudinary.config.js
```

## Database Models

### User Schema

- Username, password, email
- Role: ARTIST or GALLERY
- Description and profile image
- Genres specialization
- Location with coordinates (for maps)
- References to artworks collection

### Artwork Schema

- Title, description, date created
- Author reference (User)
- Gallery reference (User)
- Image storage (Cloudinary)
- Genre classification

## API Endpoints

- `GET /` - Home page with genre browsing
- `GET /buscador` - Search functionality
- `GET /artists/list` - List all artists
- `GET /artists/detail/:artist_id` - Artist profile
- `GET /galleries/list` - List all galleries
- `GET /galleries/detail/:gallery_id` - Gallery profile with map
- `GET /artworks/list` - Browse all artworks
- `GET /artworks/detail/:artwork_id` - Artwork details
- `GET /api` - API for users data

## Contributing

This is a portfolio project. Feel free to fork and modify for your own use.

## License

ISC
