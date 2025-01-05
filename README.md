# **Lingo Bingo** - A 72 hour full stack project by Me

```
lingo-bingo/
├── public/                # Public folder for static assets
│   ├── index.html         # Main HTML file
│   ├── logo.png           # Logo image
│   └── vite.svg           # Vite logo
├── src/                   # Source folder for app components and logic
│   ├── assets/
│   ├── icons/              # Icon assets
│   │   ├── forgetPasswordIcon.png  # Icon for "Forget Password"
│   │   ├── logoIcon.png            # Logo icon
│   │   ├── signinIcon.png          # Sign-in icon
│   │   └── userLogout.png          # Logout icon
│   ├── images/             # Image assets
│   │   └── myPhoto.jpg              # Sample photo
│   ├── sounds/             # Sound assets
│   │   └── click.mp3                # Click sound effect
│   └── react.svg           # React SVG file
|   | 
│   ├── components/        # Reusable components
│   │   ├── Buttons/       # Button-related components
│   │   │   └── LogoutWithImage.jsx # Button for logout with image
│   │   ├── Home/          # Components specific to the Home page
│   │   │   ├── AboutSection.jsx
│   │   │   ├── ImageSlider.jsx
│   │   │   ├── SuccessSection.jsx
│   │   │   ├── TestimonialsSection.jsx
│   │   ├── Banner.jsx
│   │   ├── cardShow.jsx
│   │   ├── Footer.jsx
│   │   ├── LetsLearn.jsx
│   │   ├── LoadingUI.jsx
│   │   ├── Modal.jsx
│   │   ├── NavBar.jsx
│   │   ├── VocabularyCard.jsx
│   │   └── VocabularyDetails.jsx
│   ├── contexts/          # Context API-related files
│   │   └── AuthProvider.jsx # Authentication provider for global state
│   ├── hooks/             # Custom React hooks
│   │   ├── Firebase.Config.js # Firebase configuration
│   │   └── useAuth.js     # Hook for authentication logic
│   ├── layout/            # Layout components
│   │   ├── HomeLayout.jsx # Layout for home page
│   │   └── root.jsx       # Root layout component
│   ├── pages/             # Page components
│   │   ├── AboutUs.jsx    # About Us page
│   │   ├── ContactUs.jsx  # Contact Us page
│   │   ├── Lesson.jsx     # Lesson details page
│   │   ├── Login.jsx      # Login page
│   │   ├── MyProfile.jsx  # Profile page
│   │   ├── PasswordReset.jsx # Password reset page
│   │   ├── StartLearning.jsx # Start learning page
│   │   ├── Tutorials.jsx  # Tutorials page
│   │   ├── UpdateProfile.jsx # Profile update page
│   │   └── WrongPage.jsx  # 404 Not Found page
│   ├── routes/            # Routing logic
│   │   ├── PrivateProvider.jsx # Protected route handling
│   │   └── router.jsx     # Main routing logic
│   ├── App.jsx            # Root application component
│   ├── App.css            # Global styles
│   ├── main.jsx           # Entry point for the app
│   └── config.js          # Additional configuration
├── .env                   # Environment variables
├── .firebaserc            # Firebase configuration file
├── .gitignore             # Git ignore file
├── eslint.config.js       # ESLint configuration
├── firebase.json          # Firebase project settings
├── index.html             # Main HTML file for Vite
├── package.json           # Project dependencies and metadata
├── postcss.config.js      # PostCSS configuration
├── README.md              # Documentation for the project
├── tailwind.config.js     # Tailwind CSS configuration
└── vite.config.js         # Vite configuration
```