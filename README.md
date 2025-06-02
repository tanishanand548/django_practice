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

## Create App in Django
      python manage.py startapp anand

### Open "views.py" in "anand" folder
      from django.shortcuts import render
      # Create your views here.
Find it and open it, and replace the content with this:

      from django.shortcuts import render
      from django.http import HttpResponse

      def members(request):
          return HttpResponse("Hello world!")

  
