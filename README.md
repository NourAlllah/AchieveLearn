# 34ml-course-portal
---------------------
This project is a comprehensive course portal where users can enroll in courses, complete lessons, and unlock various achievements based on their interactions. Users will receive badges for their achievements and notifications via email, with the system handling notifications asynchronously.
  
---------------------

*Features*
 - Course Enrollment: Users can enroll in courses.
 - Lesson Completion: Users can complete lessons and track their progress.
 - Achievements: Users unlock achievements based on lessons watched and comments written.
 - Badges: Users earn badges based on the number of achievements unlocked.
 - Notifications: Users receive email notifications when they unlock new achievements.
 - Asynchronous Notifications: Notifications are handled asynchronously to ensure smooth user experience.
   
---------------------
*Components Used*

Jobs:
- This project utilizes Laravel Jobs for handling background tasks and asynchronous processing. Jobs are used for tasks such as sending emails of new achievment.

Migrations:
- Database migrations are used to manage database schema changes and ensure consistency across different environments. Migrations are used to create and modify database tables.

Seeds:
- Database seeding is used to populate the database with initial data. Seeders are used to create sample data for testing purposes.

---------------------
 *Achievements*
 
 - Lessons Watched Achievements
    - First Lesson Watched
    - 5 Lessons Watched
    - 10 Lessons Watched
    - 25 Lessons Watched
    - 50 Lessons Watched
 - Comments Written Achievements
    - First Comment Written
    - 3 Comments Written
    - 5 Comments Written
    - 10 Comments Written
    - 20 Comments Written
  - Badges
    - Beginner: 0 Achievements
    - Intermediate: 4 Achievements
    - Advanced: 8 Achievements
    - Master: 10 Achievements

      
---------------------


*API Endpoints*
Achievements Endpoint
Endpoint

        GET /api/users/{user}/achievements

Response

        {
            "unlocked_achievements": ["First Lesson Watched", "5 Lessons Watched", "First Comment Written"],
            "next_available_achievements": ["10 Lessons Watched", "3 Comments Written"],
            "current_badge": "Beginner",
            "next_badge": "Intermediate",
            "remaining_to_unlock_next_badge": 3
        }
        
  - unlocked_achievements (string[]) --- An array of the user’s unlocked achievements by name.
  - next_available_achievements (string[]) --- An array of the next achievements the user can unlock by name.
  - current_badge (string)
  - next_badge (string)
  - remaining_to_unlock_next_badge (int)

     --------------------- 

*Setup and Installation*

1- Clone the repository:

        git clone https://github.com/NourAlllah/34ml_task

2- Install dependencies:

        composer install
        npm install

3- Configure the .env File:
  
      cp .env.example .env

4- update .env File:

        DB_CONNECTION=mysql
        DB_HOST=127.0.0.1
        DB_PORT=3306
        DB_DATABASE=your_database_name
        DB_USERNAME=root
        DB_PASSWORD=

        MAIL_MAILER=smtp
        MAIL_HOST=smtp.gmail.com
        MAIL_PORT=587
        MAIL_USERNAME=yourgmail@gmail.com
        MAIL_PASSWORD=create this password using google app
        MAIL_ENCRYPTION=tls
        MAIL_FROM_ADDRESS=yourgmail@gmail.com
        MAIL_FROM_NAME="${APP_NAME}"

 ***adding gmail and password is important to push email notification, If the email was not received, check the logs of your email service provider.

5- Generate Application Key:

        php artisan key:generate
        
6- php artisan migrate:

        php artisan migrate

7- clearinf config cash:

        php artisan config:clear

        php artisan config:cache 


8- Seed the database:

        php artisan db:seed


9- Start the development server:

        php artisan serve
        npm run dev 

10- Ensure that queue workers are running to handle jobs:

        php artisan queue:work

      
