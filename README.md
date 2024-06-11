# Laravel Vue.js Project

This is a full-stack web application using Laravel for the backend and Vue.js for the frontend.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Project](#running-the-project)
- [License](#license)

## Prerequisites

Before you begin, ensure you have met the following requirements:
- **PHP**: >= 7.3
- **Composer**: >= 1.9.0
- **Node.js**: >= 12.x
- **npm**: >= 6.x
- **Git**

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/your-username/your-laravel-vue-project.git
    ```

2. **Navigate to the project directory:**

    ```sh
    cd your-laravel-vue-project
    ```

3. **Install PHP dependencies:**

    ```sh
    composer install
    ```

4. **Install JavaScript dependencies:**

    ```sh
    npm install
    ```

## Configuration

1. **Copy the example environment file and make the required configuration changes in the `.env` file:**

    ```sh
    cp .env.example .env
    ```

2. **Generate a new application key:**

    ```sh
    php artisan key:generate
    ```

3. **Configure your database settings in the `.env` file:**

    ```plaintext
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=your_database_name
    DB_USERNAME=your_database_username
    DB_PASSWORD=your_database_password
    ```

## Running the Project

1. **Run database migrations:**

    ```sh
    php artisan migrate
    ```

2. **Run the development server:**

    ```sh
    php artisan serve
    ```

3. **Compile the frontend assets:**

    For development:

    ```sh
    npm run dev
    ```

    For production:

    ```sh
    npm run prod
    ```

4. **Access the project in your web browser:**

    Open your browser and navigate to `http://localhost:8000`.

## License

This project is open-source and available under the [MIT License](LICENSE).

