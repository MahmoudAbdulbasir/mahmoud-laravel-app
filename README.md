# Laravel Application — Railway Deployment + GitHub Actions CI/CD

This repository contains a Laravel application automated with **GitHub Actions** for testing and deployment to **Railway**.

**Live Application:**  
[https://mahmoud-laravel-app.up.railway.app/](https://mahmoud-laravel-app.up.railway.app/)

-----------------------------------------------------------------------------------------------------------------------------

## Technologies Used

- Laravel 10+  
- PHP 8.2  
- Composer  
- GitHub Actions (CI/CD)  
- Railway (Hosting & Deployment)

-----------------------------------------------------------------------------------------------------------------------------

## Local Setup

1. Clone the repository:

```bash
git clone https://github.com/laravel/laravel.git
cd laravel

2. Install dependencies:

```bash
composer install

3. Copy .env.example and generate app key:

```bash
cp .env.example .env
php artisan key:generate

4. Run the app locally:

```bash
php artisan serve

---------------------------------------------------------------------------------------------------------------------------------

## DEPLOYMENT

This application is deployed on Railway.

Live URL:
https://mahmoud-laravel-app.up.railway.app/

Deployment Steps:

1- Push code to the GitHub repository.

2- GitHub Actions triggers the CI/CD workflow on the main branch.

3- Workflow installs dependencies, sets up the environment, runs tests, and triggers Railway deployment via API.

4- Railway builds the container and updates the live application.

GitHub Secrets Used:

RAILWAY_TOKEN

RAILWAY_PROJECT_ID

----------------------------------------------------------------------------------------------------------------------------------

## CI/CD 

Workflow file: .github/workflows/laravel-cicd.yml

Trigger: Push to main

Steps:

1- Checkout code

2- Install PHP + Composer dependencies

3- Copy .env.example → .env

4- Generate Laravel app key

5- Run tests (php artisan test)

6- Deploy to Railway via API (if tests pass)

----------------------------------------------------------------------------------------------------------------------------------

## CHALLENGES & SOIUTIONS

1- Railway CLI Login Issues
Solved by using Railway API deploy trigger instead of CLI.

2- Missing PHP Extensions
Added mbstring, bcmath, and pdo_mysql extensions in workflow.

3- Environment Setup
.env automatically copied and app key generated in workflow.

-----------------------------------------------------------------------------------------------------------------------------------

## BEST PRACTICES FOLLOWED

1- .env not committed

2- CI/CD workflow handles build, test, deploy

3- Clear folder structure

4- Workflow compatible with Railway CLI v2

5- After push, check GitHub Actions → Laravel CI/CD for a successful run.

6- Verify Railway deployment is live.

  
