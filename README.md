![Screenshot (215)](https://user-images.githubusercontent.com/63959831/110208574-04827580-7eae-11eb-831f-fbb70ed232bd.png)

# junior_scientica
JS is one of the oldest segments of our annual techno-management fest "Sandhaan". The most interactive way to let school students have a glimpse of what college life is all about. The entire ethos of Scientica and Sandhaan is ample to get the adrenaline going.


## Current Features

### Site access features:

* User must be logged in to access the Quiz.
* For signup user is required to give *username*, *first name*, *last name*, *e-mail address* and *password*.
* For login the user will be required to enter *username* and *password* only.

### Features of the quiz:

* All questions are multiple choice question.
* Each question is displayed only once per user.
* Questions are displayed randomly for every user.
* If the user by-mistake presses refresh or go back to the previous page, there will be a new question for the user and the 
  question he/she was on will be marked as attempted.
* A message will be  displayed after every attempted question whether the answer was correct or incorrect.


### Leaderboard features:

* Leaderboard is a shorted list according to the score obtained by the users.
* If two users are having same score, the user who has signed up earlier will have good ranking than the one who joined late.
* Leaderboard is open to all. No login required.

### Administrative features:

* Only admin can add questions.
* Admin can add questions and modify them until they are not marked as *Has been published?*
* Once a question has been published, it can neither be modified nor can be accessed. Admin can only see a list of questions.
* Admin can search questions by question text or choice text.
* Admin can filter questions based on whether the questions have been published or not.


## Getting started with development
Dependencies:
- Python 3.6.x
- Django 1.11.x
- Ubuntu 17.04 or later or Linux Mint 18.2 or later

### 1. Clone this repository
```bash
git clone https://github.com/Model-Club-BIT-Sindri/junior_scientica.git
cd lets_quiz
```

### 3. Create the virtualenv
```bash
## run following command from `junior_scientica` directory
mkvirtualenv junior_scientica -a "$(pwd)" -p python3.6
```

### 4. Install python packages
```bash
## Activate the virtualenv which you created on the last step
workon junior_scientica
cd ..
pip install -r requirements.txt
```

### 5. Setup the database
*TODO - Add instructions for this when I start using MySQL database.*

### Change DataBase from AWS to sqlite3 
*(IMPORTANT IF YOUR NOT A DEVLOPER AT MODEL CLUB)*
Replace below code from settings.py 


```DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'demo_1',
        'USER': 'imran',
        'PASSWORD':'nazir326',
        'HOST':'database-1.c8wv9hegmm83.us-east-2.rds.amazonaws.com',
        'PORT':'5432',
    }
}
```
To

```DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```
### 6. Run database migrations
```bash
cd lets_quiz
python manage.py migrate
```
Please note - settings.py currently has AWS database set to default with no outbounds success Therefore Follow the above steps if you are not a devloper at MODEL CLUB.



### 7. Create superuser
```bash
python manage.py createsuperuser
```

### 8. Run development server
```bash
python manage.py runserver
```
