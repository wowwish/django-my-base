Host on Python Anywhere:
* Under 'ALLOWED_HOSTS' in the 'settings.py' file of your Django Project, add 'vavish.pythonanywhere.com'
* Also make sure to set 'DEBUG = False' in your Project's 'settings.py' File. This prevents from Django showing error stacktraces and makes the Deployment Secure. 
* Go to www.pythonanywhere.com and Login
* Go to Console > Bash and type the following:
	```
	mkvirtualenv --python=python3.8 myproj # To create a virtual environment for the Project
	pip list # To check installed default packages
	pip install -U django==4.1.1 # Install Django version 4.1.1 (and any other plotting or machine-learning packages used in the Project)
	which django-admin.py # Check for proper installation of Django
	git clone https://github.com/wowwish/django-my-base.git # Clone your Project Repo
	cd django-my-base/learning_templates/ # To perform Django administrative tasks
	python manage.py migrate
	python manage.py makemigrations basic_app
	python manage.py migrate
	python manage.py createsuperuser # Create admin user
	python manage.py collectstatic # Copy static files to the STATIC_ROOT folder
	```
* Go to Dashboard > Web > add a new web app > Copy and keep the domain name > select Manual Configuration > Next > Create the Hello World App
* Next, Configure the Hello World App > Enter a path to the Virtualenv > Fill with '/home/Vavish/.virtualenvs/myproj'
* Next, Enter '/home/Vavish/django-my-base/learning_templates' in the Source Code location Box of the Web Dashboard
* Next, edit the 'wsgi.py' configuration file from the Code section of the Web Dashboard > Remove the Hello World Application Specific Code
* Edit the Django Setup Boilerplate Code > Setup the Source code Path to point to '/home/Vavish/django-my-base/learning_templates' here as well.
* Also change the settings file name to 'learning_templates.settings' for the DJANGO_SETTINGS_MODULE environment variable using 'os.environ.setdefault()' 
* Add the following to setup the Django App before the Application is Initialized and Launched through Code:
	```
	import django
	django.setup()
	```
* Setup Static Files: 
	- Set the URL for '/static/admin' to be '/home/Vavish/.virtualenvs/myproj/lib/python3.8/site-packages/django/contrib/admin/static/admin'
	- Set the URL for '/static/' (STATIC_URL) to be '/home/Vavish/django-my-base/learning_templates/static_root' (STATIC_ROOT)
* Finally, Reload the Web App and Check. REMEMBER: THE WEB APP HAS TO BE RELOADED FOR ANY CHANGES TO TAKE EFFECT.
