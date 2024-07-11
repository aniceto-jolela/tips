<div style="text-align: center;" markdown="1">

# Installing the **django** correctly
#
![icons8-django-50.png](../assets/django/icons8-django-50.png) <span style="margin-right:50px" />
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
```shell
django-admin startproject web
```

> [!NOTE]
> **django-admin startproject** => Command to create the project
> 
> **web** => Project Name
> 
> This command created a new project.
> ![start-project.png](../assets/django/start-project.png)
