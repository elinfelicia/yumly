# 🍽️ Yumly - Recipe Collection App

A modern, responsive web application for discovering, browsing, and exploring delicious recipes. Built with Vue 3, Vue Router, and Vite.

## 📋 Project Description

Yumly is a recipe collection application that allows users to:
- Browse all available recipes
- Filter recipes by category
- Search for recipes by name or description
- View detailed recipe information including ingredients and cooking instructions
- Leave comments and ratings on recipes

## 🏗️ Project Structure

```
yumly/
├── src/
│   ├── components/          # Reusable Vue components
│   │   ├── AppHeader.vue
│   │   ├── AppFooter.vue
│   │   ├── RecipeCard.vue
│   │   ├── CategoryList.vue
│   │   ├── SearchBar.vue
│   │   ├── RatingStars.vue
│   │   ├── CommentSection.vue
│   │   └── Loader.vue
│   ├── views/               # Page components
│   │   ├── HomeView.vue
│   │   ├── CategoryView.vue
│   │   └── RecipeView.vue
│   ├── router/              # Vue Router configuration
│   │   └── index.js
│   ├── data/                # Mock data
│   │   └── mockRecipes.js
│   ├── assets/              # Static assets and styles
│   ├── App.vue              # Root component
│   └── main.js              # Application entry point
├── public/                  # Public static files
└── package.json
```

## 🚀 Features

### Home Page
- Display all recipes in a responsive grid
- Search functionality to filter recipes in real-time
- Category sidebar with recipe counts
- Click on categories to filter by category

### Category Page
- Display recipes filtered by selected category
- Active category is visually highlighted
- Shows recipe count for the category

### Recipe Detail Page
- Full recipe information including:
  - Recipe image
  - Rating display
  - Cooking time and ingredients count
  - Description
  - Ingredients list
  - Step-by-step instructions
- Comment section with:
  - Form to submit comments (name and text required)
  - Validation for required fields
  - Success message after submission
  - List of all comments with timestamps

## 🛠️ Technologies Used

- **Vue 3** - Progressive JavaScript framework
- **Vue Router** - Official router for Vue.js
- **Vite** - Next-generation frontend build tool
- **Pinia** - State management (configured but using mock data for now)

## 📦 Installation

1. Clone the repository
```bash
git clone <repository-url>
cd yumly
```

2. Install dependencies
```bash
npm install
```

## 🎯 Development

### Start Development Server
```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the next available port).

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

## 📝 Data

Currently, the application uses mock data stored in `src/data/mockRecipes.js`. The data includes:
- 10 sample recipes across 5 categories (Desserts, Main Courses, Appetizers, Vegetarian, Breakfast)
- Each recipe includes:
  - Name, image, rating, cooking time
  - Ingredients list
  - Step-by-step instructions
  - Category information
  - Comments (initially empty)

## 🎨 Design Features

- **Responsive Design**: Works on mobile, tablet, and desktop
- **Modern UI**: Clean, intuitive interface with consistent styling
- **Component-Based Architecture**: Reusable components for maintainability
- **Loading States**: Loading indicators for better UX
- **Form Validation**: Client-side validation for comment submission

## 🔄 Future Enhancements

When the backend API is ready, the application can be easily updated to:
- Fetch recipes from API endpoints
- Submit comments to the backend
- Implement user authentication
- Add recipe rating functionality
- Support recipe creation and editing

## 📚 Learning Resources

- [Vue 3 Documentation](https://vuejs.org/)
- [Vue Router Documentation](https://router.vuejs.org/)
- [Vite Documentation](https://vitejs.dev/)

## 👥 Team

**Team Number:** [Your Team Number]

**Team Members:**
- [Team Member 1] - [GitHub Username]
- [Team Member 2] - [GitHub Username]
- [Add more team members as needed]

## 📋 Project Planning

Project planning is managed in GitHub Projects. [Add link to your GitHub Projects board]

## 📅 Daily Logs

Daily work logs are documented in `/docs/daily-log/` directory.
Format: `YYYY-MM-DD.md`

## 📄 License

This project is part of a course assignment.
