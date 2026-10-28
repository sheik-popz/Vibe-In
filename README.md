# VibeIn – Music Streaming Application

A web-based music streaming application where users can sign up, browse albums, open album details and play songs in a built-in audio player. Admins can add new albums with songs, posters and thumbnails from a private admin panel.

**Live site:** https://music-streaming-application-ten.vercel.app/

## About the project

VibeIn is a mini project that shows how a complete music app can be built with React and Firebase, without writing a separate backend server. Firebase handles sign-in and the album data, and Cloudinary stores the images and audio files. Normal users listen to music, and users with the admin role can upload new albums.

## Features

- Register with email and password, with an email verification step
- Login, logout and forgot password
- Home page showing all albums as poster cards
- Album details page with title, number of tracks, release date, languages and description
- Song list with track number, song name, singers, music director, mood and duration
- Built-in audio player with play and pause controls
- User account area: view profile, update profile picture, update profile, change password and delete account
- Admin panel to add albums with a poster, song files, song thumbnails, singers, director and mood
- Role-based access, so admin pages open only for admin users
- Protected routes for logged-in users and public routes for login and register
- Loading spinner and toast notifications for success and error messages
- Responsive layout built with Tailwind CSS

## Tech stack

- React 19 with Vite
- React Router for page navigation
- Tailwind CSS 4 for styling
- Firebase Authentication for sign-up, login and email verification
- Cloud Firestore for album and user data
- Cloudinary for image and audio file uploads
- react-pro-audio-player for playback
- React Hot Toast for notifications and React Icons for icons
- Firebase Hosting for deployment

## Project structure

```
.
├── index.html
├── package.json
├── vite.config.js
├── firebase.json                  # Firebase Hosting settings
├── public/
└── src/
    ├── App.jsx
    ├── main.jsx
    ├── auth/                      # Login, Register, ForgetPass
    ├── backend/                   # Firebase configuration
    ├── components/
    │   ├── admin/                 # AddAlbum, AdminDashboard, AdminLayout, AdminSidebar
    │   ├── home/                  # Dashboard, AlbumDetails, Sidebar
    │   ├── navigation bar/        # Logo, Menu, Navbarcontainer
    │   └── user/                  # Account, profile, picture, password, delete user
    ├── context/                   # AlbumContext, AuthContext, UserContext
    ├── helpers/                   # Loading spinner
    ├── pages/                     # Home, Layout, PageNotfound
    └── routes/                    # Routes, Publicroutes, Protectedroutes, Adminroutes
```

## Run locally

1. Download or clone this repository.
2. Install the packages:
   ```
   npm install
   ```
3. Start the development server:
   ```
   npm run dev
   ```
4. Open the address shown in the terminal, usually http://localhost:5173

To create a production build, run `npm run build`. The output goes to the `dist` folder.

## Set up your own Firebase and Cloudinary

1. Create a project at https://console.firebase.google.com and turn on **Authentication** (Email/Password) and **Cloud Firestore**.
2. Copy your web app settings into `src/backend/Firebaseconfig.js`.
3. Create a Cloudinary account, then add an **unsigned upload preset** and update the cloud name and preset name in `AddAlbum.jsx` and `UpdatePicture.jsx`.
4. To make a user an admin, set the `role` field to `admin` on that user's document in Firestore.
5. Set Firestore security rules so only admins can write albums.

## Deploy

```
npm run build
firebase deploy
```

## Note

This project was built for learning. For real use, keep Firestore security rules strict and use signed uploads for Cloudinary.
