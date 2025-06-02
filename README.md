## 🛠️ Installing of Django in VS Code

### 1. Create and activate a virtual environment

Open a terminal inside VS Code:
      
      python -m venv tanXelv(any name)

Then activate it:<br>

 Windows (PowerShell):

    .\tanXelv\Scripts\Activate

macOS/Linux:

    source tanXelv/bin/activate

### 2. Install Django
    pip install django

### 3. Start a Django project
    django-admin startproject tanish(name of project will be different from virtual environment name)
    cd tanish

### 4. Run the development server
    python manage.py runserver
You’ll see:

    Starting development server at http://127.0.0.1:8000/
## 📁 Project Structure Overview
    myproject/
    ├── manage.py
    └── myproject/
        ├── __init__.py
        ├── settings.py
        ├── urls.py
        └── wsgi.py

## ✨ Create App in Django
      python manage.py startapp anand

### Open "views.py" in "anand" folder
      from django.shortcuts import render
      # Create your views here.
Find it and open it, and replace the content with this:

      from django.shortcuts import render
      from django.http import HttpResponse

      def members(request):
          return HttpResponse("Hello world!")
Create a file named "urls.py" in the same folder as the "views.py" file, and type this code in it:<br>
tanish/anand/urls.py:
            
      from django.urls import path
      from . import views

      urlpatterns = [
          path('anand/', views.anand, name='anand'),
      ]

include the path in tanish/tanish/urls.py:
      
      from django.contrib import admin
      from django.urls import include, path

      urlpatterns = [
          path('', include('anand.urls')),
          path('admin/', admin.site.urls),
      ]
this will route users that comes in via "127.0.0.1:8000"

### Templates in Django
Create a "templates" folder inside the "anand" folder, and create a HTML file named "djproject.html"<br>
tanish/anand/templates/djproject.html:

      <!DOCTYPE html>
      <html>
      <body>

      <h1>Hello World!</h1>
      <p>Welcome to my first Django project!</p>

      </body>
      </html>
Open the views.py file in the members folder, and replace its content with this:

      from django.http import HttpResponse
      from django.template import loader

      def anand(request):
        template = loader.get_template('djproject.html')
        return HttpResponse(template.render())
Change Settings:- work with more complicated stuff than "Hello World!", We have to tell Django that a new app is created<br>
"settings.py" file in the "tanish" folder<br>
add the "anand" app like this:

      INSTALLED_APPS = [
          'django.contrib.admin',
          'django.contrib.auth',
          'django.contrib.contenttypes',
          'django.contrib.sessions',
          'django.contrib.messages',
          'django.contrib.staticfiles',
          'anand'
      ]
run this command:

      python manage.py migrate
after
      
      python manage.py runserver
      "http://127.0.0.1:8000/anand/" run this in the address bar
