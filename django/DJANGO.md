<div style="text-align: center;" markdown="1">

# Installing the `django` correctly
#
![icons8-django-50.png](../assets/django/icons8-django-50.png)
![icons8-linux.gif](../assets/django/icons8-linux.gif)
</div>

#### Check if Python Is Installed on Ubuntu
```shell
python3
```

> [!IMPORTANT]
> If you have not installed the python on your machine, run this command below:

~~~shell
sudo apt install python3
~~~
~~~shell
python3 --version
~~~
```shell
sudo apt update
```

> [!CAUTION]
> Avoids installing Django in the global virtual environment of the operational system. Create your own virtual environment to avoid conflict with __root__.

### Let's create a new environment variable.
#
- Step 1
```shell
python3 -m venv ~/web_env
```
> [!NOTE]
> **python3 -m venv** ⇢ Command to create the virtual environment.
> 
> > **~/** ⇢ Virtual environment path.
> 
> **web_env** ⇢ Virtual environment Name.
> 
![create-env.png](../assets/django/create-env.png)
- Step 2

> [!WARNING]
> The path is where the new environment will be saved on your computer.
> 
>The final step in setting up your virtual environment is to activate it:

```shell
source ~/web_env/bin/activate
```
![open-env.png](../assets/django/open-env.png)
- Step 3

> [!TIP]
> After you’ve created and activated a virtual environment, enter the command:

```shell
pip install django
```
![django-install.png](../assets/django/django-install.png)
- Step 4

```shell
python -m django --version
```
![version.png](../assets/django/version.png)
- Step 5

```shell
django-admin
```
> List all commands of Django.
> ![django-admin.png](../assets/django/django-admin.png)
> 

### Let's create a new project

1)
```shell
django-admin startproject web
```

> [!NOTE]
> **django-admin startproject** ⇢ Command to create the project
> 
> **web** ⇢ Project Name
> 
> This command created a new project.
> ![start-project.png](../assets/django/start-project.png)
2)
> Enter the project folder.
![cd-web.png](../assets/django/cd-web.png)

3)

> [!IMPORTANT]
> Opens the `settings.py` file and comments on the `DATABASES`

<details>
    <summary> File location </summary>
    a) <img width="50px" src="../assets/django/1.png" />
    b) <img width="50px" src="../assets/django/2.png" />
    c) <img width="50px" src="../assets/django/3.png" />
    d) <img width="50px" src="../assets/django/4.png" />
    e) <img width="50px" src="../assets/django/5.png" />
</details>

> [!CAUTION]
> Before
> ![before.png](../assets/django/before.png)

> [!TIP]
> After
> ![after.png](../assets/django/after.png)


 Now run the `manage.py` file
```shell
python manage.py runserver
```
 > [!NOTE]
 > You are to be congratulated now you have your first Django project installed.
 
![run.png](../assets/django/run.png)
![localhost.png](../assets/django/localhost.png)
![admin.png](../assets/django/admin.png)

#
![Congratulations.gif](../assets/gifts/Congratulations.gif)