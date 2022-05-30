# JKET Parents/Guardians Registration Project

## What is this application?:
###### This application is made for [Japan Kauri Education Trust](http://jket.epizy.com/index.php) in Auckland, New Zealand where they hold a few Japanese classes everyday.At the moment they use a pen and paper when parents drop-off/pick-up their children. This simple application allows JKET admins and parents/guardians to have a central location to record drop-offs/pick-ups as well as to check logs. Even more, they can save cost of papers!
---

## Technology:
- Django framework
---

## How to run this project:

1. Once clone or download this code, [create a virtualenv](https://docs.python.org/3/library/venv.html).
2. Acticate the virtualenv.
3. From terminal, install all the requirements with `pip install -r requirements.txt`.
4. From terminal, run `python manage.py shell`. Then run below 3 lines of commands to generate a secret key.
`from django.core.management.utils import get_random_secret_key`
`print(get_random_secret_key())`
`exit()`
5. Copy the generated secret key into *settings.py* in *rego* folder, where it says `SECRET_KEY = `. Replace `os.getenv("SECRET_KEY")` with the generated secret key(make sure to put "" around it).
6. From terminal, run `python manage.py runserver` and go to 127.0.0.1:8000/interaction to view the landing page.

---

## How to use this project:

### Situation1 --- When a parent/guarding drops off/picks up their kid.
- Default PIN set for all users are 123456.
- 127.0.0.1:8000/interaction for landing page.
- Default language is en(English). The second choice is ja(Japanese).
- 127.0.0.1:8000/interaction/classroom_list/ displays only classes happening today.
- Selecting a particular class displays a list of students.
- Selecting a particular student takes the user to the check-in/out page where she is asked to select 2 choices(Drop-off or Pick-up) as well as PIN. In case she forgot her PIN, clicking ***Forgot your PIN?*** link below the PIN field takes her to ***JKET PIN Reset Portal*** where she can send a ***PIN reset link*** to her registered email address (at the moment it's sent to console). Once a new PIN is set via her phone etc. right there, she can go back to the landing page of Registration app by selecting ***Back to Find Child*** link on the app screen. 

### Situation2 --- When a JKET admin person receives PIN reset request from an user:
- Use ***Lost PIN?*** link in 127.0.0.1:8080/accounts/login/ to send a ***PIN reset link*** to the user.
- Use ***If someone else needs PIN reset, click here*** link in 127.0.0.1:8080/accounts/password_change/ (after the admin person logs into ***JKET PIN Reset Portal***) to send a ***PIN reset link*** to the user(at the moment it's sent to console).
- Use 127.0.0.1:8080/admin to reset from the admin portal under User section.

### Situation3 --- When parents and JKET staff want to change PIN.
- 127.0.0.1:8080/accounts/login/ to change their PIN whenever they want.

### Situation4 --- When JKET admin need to administration work.
- 127.0.0.1:8080/admin to add/change student/staff/classroom details as well as view drop-off/pickup logs.
- ***JKETAdmin*** group has Modify access. ***JKETTeachers*** group has Read-Only access.

---

## Lastly:
###### JKET is a NPO, therefore I wanted to create this application to save their running cost/labour. Introducing PIN and having JKET admin to process user's PIN reset inquiries is my current concern so once I get user feedback I am going to focus on more usability:-)
