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

#### Now install [Anaconda](https://www.anaconda.com/download), after which you can continue with the tutorial.⇣⇣⇣

### Let's create a new environment variable.
#
- Step 1
```shell
python3 -m venv ~/my_environment_env
```
or
```shell
python -m venv ~/my_environment_env
```
or also
```shell
python -m venv my_environment_env
```
> [!NOTE]
> **python3 -m venv** ⇢ Command to create the virtual environment.
> 
> > **~/** ⇢ Virtual environment path.
> 
> **my_environment_env** ⇢ Virtual environment Name.
> 
![0.png](../assets/django/anaconda/0.png)
- Step 2

> [!WARNING]
> The path is where the new environment will be saved on your computer.
> 
>The final step in setting up your virtual environment is to activate it:

```shell
source ~/my_environment_env/bin/activate
```
![1.png](../assets/django/anaconda/1.png)

- Step 3

> [!TIP]
> After you’ve created and activated a virtual environment, enter the command:

```shell
pip install django
```
![2.png](../assets/django/anaconda/2.png)
- Step 4

```shell
python -m django --version
```
![3.png](../assets/django/anaconda/3.png)
- Step 5

```shell
django-admin
```
> List all commands of Django.
> ![4.png](../assets/django/anaconda/4.png)
> 

### Let's create a new project

1)
```shell
django-admin startproject store
```

> [!NOTE]
> **django-admin startproject** ⇢ Command to create the project
> 
> **store** ⇢ Project Name
> 
> This command created a new project.
> ![5.png](../assets/django/anaconda/5.png)
2)
> Enter the project folder.
![6.png](../assets/django/anaconda/6.png)

3)
> Create the sqlite3 database
```shell
python3 manage.py migrate
```
![7.png](../assets/django/anaconda/7.png)

 Now run the `manage.py` file
```shell
python manage.py runserver
```
 > [!NOTE]
 > You are to be congratulated now you have your first Django project installed.
 
![8.png](../assets/django/anaconda/9.png)
![10.png](../assets/django/anaconda/10.png)
![11.png](../assets/django/anaconda/11.png)

#
[1.webp](../assets/gifts/1.webp)