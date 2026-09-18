# Bloom Recipes Remastered 🌸

A remastered version of my 2023 academic recipe platform, built with Vue 3 and a Laravel REST API.

Bloom allows users to explore recipes, search and filter results, view preparation details, like recipes, and save favorites. It also includes an administration interface for managing recipe content and publication.

This project revisits an existing application to improve its data quality, functionality, and user experience while documenting my growth as a developer.

## Project Links

- [**Live demo**](https://bloomrecipes.vercel.app/)

> **Demo loading note:** The demo may occasionally take longer to load recipe data. If no recipes appear, please wait a moment and refresh the page.

- [**Original 2023 repository**](https://github.com/MoniAF/BloomRecipesWebsite)

## Features

### Recipe Discovery

- Browse published recipes and view their details.
- Search recipes by name.
- Filter recipes by category, occasion, and difficulty.
- View ingredients, quantities, preparation instructions, portions, and preparation and cooking times.
- Explore a trending section based on recipe likes.

### User Accounts

- Register and sign in.
- Like recipes and remove likes.
- Save recipes to revisit later.
- Receive visual feedback when a recipe is saved.

### Administration

- Sign in through a dedicated admin interface.
- Create recipes with images and associated recipe information.
- Manage recipe ingredients.
- Publish and unpublish recipes.
- Review unpublished recipes and recipe details.

## Technology Stack

| Area | Technologies |
| --- | --- |
| Frontend | Vue 3, Vite, JavaScript, HTML, SCSS, Bootstrap |
| API integration | Axios, REST API |
| Backend | PHP, Laravel 10 |
| API authentication | Laravel Sanctum |
| Admin interface | Laravel Blade |
| Local database | MariaDB through Laragon |
| Version control | Git, GitHub |

## From the Original to the Remaster

The original version was developed in 2023 as an academic project and was my first experience using Vue through a CDN. The remaster builds on that foundation.

| Area | Remastering work |
| --- | --- |
| Frontend structure | Migrated the frontend from Vue through a CDN to a Vue 3 + Vite project. |
| Database | Cleaned duplicate data, unnecessary spaces, damaged characters, and records missing category associations. |
| API | Extended and refined authentication, recipe filtering, likes, and saved-recipe functionality. |
| Administration | Added and refined recipe creation and publication workflows. |
| Interface | Renewed the layout, recipe presentation, difficulty labels, and interaction feedback. |
| Images | Replaced missing original recipe images with AI-generated illustrations. |

## How It Works

The Vue frontend requests recipe data from the Laravel REST API through Axios. Laravel handles application logic and database access, while Sanctum provides token-based authentication for protected user actions.

The administration interface uses Laravel Blade views to support recipe management and publication workflows.

## Demo Account

Use this shared demo account to explore features such as liking and saving recipes:

- **Email:** afmonica@gmail.com
- **Password:** remaster1234

This account has regular user permissions. Likes and saved recipes are shared across visitors and may change as others try the application. Please do not enter personal information.

## Local Setup

### Database

This project uses **MariaDB** as its relational database management system. The database can be restored locally using **Laragon**:

1. Start Laragon and its database service.
2. Open the database manager included with Laragon.
3. Create or select the database for the project.
4. Import and execute the provided `.sql` file.

### Backend

Navigate to the Laravel project:

```bash
cd proyectobloom
```

Install dependencies:

```bash
composer install
```

Create the environment file:

```bash
cp .env.example .env
```

Configure the database connection in `.env` using your local settings. For example:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=proyectobloom
DB_USERNAME=root
DB_PASSWORD=
```

Make sure `DB_DATABASE` matches the database where you imported the SQL file.

Generate the application key:

```bash
php artisan key:generate
```

Create the storage link:

```bash
php artisan storage:link
```

Recipe images must also be available in the storage location expected by the application. Importing the database does not restore the image files.

Start the Laravel server:

```bash
php artisan serve
```

The backend will run by default at:

```text
http://127.0.0.1:8000
```

Example API endpoint:

```text
http://127.0.0.1:8000/api/recipes/all
```

### Frontend

The frontend uses **Vue 3 and Vite** and requires **Node.js and npm**.

Open a separate terminal and navigate to the frontend directory from the repository root:

```bash
cd bloomrecipes
```

Install dependencies:

```bash
npm install
```

Configure the backend URL in `bloomrecipes/src/services/api.js`:

```javascript
export const BACKEND_URL = 'http://127.0.0.1:8000'
```

Do not include `/api/` in `BACKEND_URL`; Axios already appends it in its configuration:

```javascript
baseURL: `${BACKEND_URL}/api/`,
```

Start the Vite development server:

```bash
npm run dev
```

Open the local URL displayed in the terminal, usually:

```text
http://localhost:5173
```

Keep the database service, Laravel server, and Vite development server running while using the application locally.


## My Role and Learning

I directed the remastering process, selected the improvements, made interface and functionality decisions, integrated frontend and backend changes, and manually tested the application.

The work gave me practice maintaining an existing codebase, cleaning relational data, connecting a Vue frontend to a Laravel API, troubleshooting authentication and image storage, and improving feedback for user actions.

## AI Assistance

I used artificial intelligence (AI) throughout the remastering process to help plan improvements, generate and revise portions of the code, troubleshoot errors, and understand the proposed solutions.

My role included defining the project's goals, making design and functionality decisions, adapting and integrating suggestions, and manually testing the application.

Recipe images were also generated with AI. They serve as visual illustrations and may not accurately represent each recipe's ingredients or final result.

This project reflects both my learning process and my experience incorporating AI assistance into a development workflow.

## Author

🌸 **Mónica Artavia Flores**

- [GitHub — MoniAF](https://github.com/MoniAF) 
- [LinkedIn — Monica Artavia Flores](https://www.linkedin.com/in/monica-artavia-flores/)


