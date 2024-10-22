# Deploy on Render

![render](../assets/django/render/django-render.jpg)
###

To deploy your Django project from GitHub using Render, follow these steps:

### 1. Create a Render Account

- Visit Render and sign up for a free account. 
- You can sign up using GitHub, which makes it easier to connect your repositories.

### 2. Prepare Your Django Project
##### Install Gunicorn
Gunicorn is essential for serving your Django application. Run the following command in your project directory:

```bash
pip install gunicorn
```
##### Update `settings.py`
Make sure to:

- Set DEBUG = False.
- Configure ALLOWED_HOSTS to include your Render domain (you can use a wildcard for testing: ALLOWED_HOSTS = ['*']).

##### Create a `requirements.txt`
Ensure all dependencies are listed in **requirements.txt**. You can generate this file by running:
```bash
pip freeze > requirements.txt
```
#### Static Files
Collect static files by running:
````bash
python manage.py collectstatic
````

### 3. Push Your Project to GitHub
If you haven’t done so already, create a GitHub repository and push your local Django project to it. Use the following commands:
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin <your-repo-url>
git push -u origin main
```

### 4. Deploy on Render
##### Create a New Web Service

- In your Render dashboard, click on the "New" button and select "Web Service."
- Connect your Render account to GitHub if prompted, and authorize access to your repositories.
- Select the repository you just pushed your Django project to.

##### Configure Your Service

- **Name**: Give your service a unique name.
- **Branch**: Select the branch you want to deploy (typically main).
- **Runtime**: Choose Python.

##### Add Environment Variables

- Scroll down to the "Advanced" section.
- Click on "Add Environment Variable" and set any necessary variables, such as database URLs or secret keys.

##### Create the Web Service
After configuring everything, click on "Create Web Service." Render will start building and deploying your application.

### 5. Access Your Live Application
Once the deployment is complete, Render will provide you with a default URL where your application is live. Click on this URL to view your Django app.

###
# Additional - requirements ✳️

Where to Create `requirements.txt`

> **Location**: You should create the requirements.txt file in the root **directory** of your Django project. This is typically where your manage.py file is located.

How to Populate `requirements.txt`
Using `pip freeze`

**Activate Your Virtual Environment:** If you are using a virtual environment (recommended), activate it:

- On Windows:
```shell
myenv\Scripts\activate
```
- On macOS/Linux:
```shell
source myenv/bin/activate
```
- **Install Dependencies:** Make sure all required packages for your Django project are installed in the virtual environment.
- **Generate requirements.txt:** Run the following command to create the file with all installed packages:

```shell
pip freeze > requirements.txt
```
This command captures all currently installed packages and their versions, outputting them into `requirements.txt`

#### Using pipreqs (for a cleaner list)
If you want to generate a more concise list that only includes the packages you actually imported in your code, consider using pipreqs:

**Install pipreqs:**
```shell
pip install pipreqs
```
**Run pipreqs:** Navigate to your project directory and run:
```shell
pipreqs . --force
```
This will create or overwrite the existing requirements.txt file based on the imports in your project files

###
# Additional - start command ✳️

To start your Django application on Render, you need to specify the start command in your Render service settings. Here’s how to do it:

#### Start Command for Render

- **Using Gunicorn**: The recommended way to serve a Django application in production is by using Gunicorn. Your start command should look like this:
```shell
gunicorn myproject.wsgi:application
```
 Replace myproject with the actual name of your Django project directory.

- **Using Uvicorn (for ASGI):** If you're using Django with ASGI (for example, if you're using Django Channels), you can use Uvicorn:
```shell
uvicorn myproject.asgi:application --host 0.0.0.0 --port 8000
```
Setting Up in Render
- **Go to Your Service Settings:** After creating your web service on Render, navigate to the service settings.
- **Edit Start Command:** In the "Start Command" field, enter one of the commands mentioned above based on whether you are using WSGI or ASGI.
- **Save Changes:** Make sure to save your changes and redeploy if necessary.

Example of a Complete Setup
If your project is named mysite, your start command would be:

```bash
gunicorn mysite.wsgi:application
```
###
# Additional - NAME_OF_VARIABLE ✳️

 #### Render Documentation

**Default Environment Variables**: Render provides a list of default environment variables that are available at runtime. You can find these variables, such as `RENDER_EXTERNAL_URL` or `RENDER_SERVICE_NAME`, along with their values in the Render documentation.

#### Application-Specific Variables
Common Environment Variables for Django:

- `DATABASE_URL`: The connection string for your database (e.g., PostgreSQL).
- `SECRET_KEY`: A secret key used by Django for cryptographic signing.
- `DEBUG`: Set to ``False`` in production environments.

You can define these variables based on your application’s requirements. For example:

```shell
DATABASE_URL=postgresql://user:password@hostname:port/dbname
SECRET_KEY=your_secret_key
DEBUG=False
```
#### Adding Variables in Render

- Once you have identified the necessary environment variables, you can add them in the Render dashboard:
- - Navigate to your service settings.
- - Click on Environment and then + Add Environment Variable.
- - Enter the key (e.g., DATABASE_URL) and its corresponding value (e.g., your database connection string).
