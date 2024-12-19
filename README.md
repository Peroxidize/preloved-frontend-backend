# Preloved - Software Documentation

## Table of Contents
- [Technology Stack](#technology-stack)
- [Installation Guide](#installation-guide)
  - [Frontend Setup](#frontend-setup)
  - [Backend Setup](#backend-setup)
  - [Database Setup](#database-setup)
  - [Deployment Notes](#deployment-notes)
- [User Access Guide](#user-access-guide)
  - [Administrator Access](#administrator-access)
  - [Seller Guide](#seller-guide)
  - [Customer Guide](#customer-guide)

## Technology Stack

### Frontend
- React v18.2.0
- Vite v5.0.0
- TypeScript v5.3.3

### Backend
- Django v5.1.4
- PyTorch v2.4.1
- ChromaDB v0.5.11

### Database
- MySQL (Latest stable version)

## Installation Guide

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   ```

3. Activate the virtual environment:
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Database Setup

1. Install MySQL on your machine if not already installed

2. Create a new MySQL database:
   ```sql
   CREATE DATABASE preloved;
   CREATE USER 'prelovedadmin'@'localhost' IDENTIFIED BY 'prelovedSE2324';
   GRANT ALL PRIVILEGES ON preloved.* TO 'prelovedadmin'@'localhost';
   FLUSH PRIVILEGES;
   ```

3. Run Django migrations:
   ```bash
   python manage.py migrate
   ```

4. Create a superuser account:
   ```bash
   python manage.py createsuperuser
   ```
   
## Deployment Notes

When deploying the application:

1. Update CORS settings in `preloved/settings.py`:
   ```python
   CORS_ALLOWED_ORIGINS = [
       "https://your-production-frontend-url.com",
       "https://api.your-backend-url.com",
   ]
   ```

2. Configure production environment variables
3. Set up proper security measures
4. Follow Django deployment best practices

For detailed deployment instructions, refer to DigitalOcean's comprehensive guide on [How to Set Up Django with Postgres, Nginx, and Gunicorn on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu).

## User Access Guide

### Administrator Access
1. Access the Django admin panel at `/admin`
2. Log in using the superuser credentials created during setup
3. From here you can:
   - Review seller verification documents
   - Create vouchers

### Seller Guide
1. Create a Seller Account:
   - Navigate to the signup page
   - Click the "create seller account" button
   - Fill in required information
   - Submit account for verification

2. Account Verification:
   - Upload required verification documents
   - Wait for admin approval

3. After Approval:
   - Log in to your seller dashboard
   - List items for sale
   - Manage inventory
   - Handle customer inquiries
   - Process orders

### Customer Guide
1. Account Creation:
   - Visit the signup page
   - Complete registration form
   - Verify email address

2. Shopping:
   - Browse available items
   - Use search filters to find specific clothing
   - View detailed product information

3. Product Interaction:
   - Add items to cart
   - Use "Buy Now" for immediate purchase
   - Chat with sellers for inquiries
   - Save items to collections

4. Purchase Process:
   - Review cart items
   - Confirm purchase
   - Track order status

