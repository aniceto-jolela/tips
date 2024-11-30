<div style="text-align: center;" markdown="1">

# Creating `API` with `django-api-rest-framework`

</div>

#### Check if [Python](https://www.python.org/downloads/), [Anaconda](https://www.anaconda.com/download) and [Django](https://www.djangoproject.com/download/) Is Installed on Ubuntu

> if you want download to see all files [store.zip](store.zip)

### Let's create a new `app`.
#
- Step 1
```shell
django-admin startproject your_project
```
- Step 2
```shell
django-admin startapp your_app
```
- Step 3 
#### Install using pip, including any optional packages you want.

- - ```shell 
    pip install djangorestframework
    pip install markdown       # Markdown support for the browsable API.
    pip install django-filter  # Filtering support
    ```
- Step 4
####  Add `'rest_framework'` to your INSTALLED_APPS setting.
- - ```py
    INSTALLED_APPS = [
        ...
        'rest_framework',
    ]
    ```
- Step 4
#### If you're intending to use the browsable API you'll probably also want to add REST framework's login and logout views. Add the following to your `root urls.py` file.
- - ```py
    urlpatterns = [
    ...
    path('api-auth/', include('rest_framework.urls'))
    ]
    ```
> [!NOTE]
> Note that the URL path can be whatever you want.
#
- Step 5
#### Any global settings for a REST framework API are kept in a single configuration dictionary named REST_FRAMEWORK. Start off by adding the following to your `settings.py` module:
- - ```py
    REST_FRAMEWORK = {
        # Use Django's standard `django.contrib.auth` permissions,
        # or allow read-only access for unauthenticated users.
        'DEFAULT_PERMISSION_CLASSES': [
            'rest_framework.permissions.DjangoModelPermissionsOrAnonReadOnly'
        ]
    }
    ```
- Step 6
#### Don't forget to make sure you've also added `rest_framework` to your `INSTALLED_APPS`.
#### We're ready to create our API now. Here's our project's root `urls.py` module:
- - ```py
    from django.urls import path, include
    from django.contrib.auth.models import User
    from rest_framework import routers, serializers, viewsets
    
    # Serializers define the API representation.
    class UserSerializer(serializers.HyperlinkedModelSerializer):
        class Meta:
            model = User
            fields = ['url', 'username', 'email', 'is_staff']
    
    # ViewSets define the view behavior.
    class UserViewSet(viewsets.ModelViewSet):
        queryset = User.objects.all()
        serializer_class = UserSerializer
    
    # Routers provide an easy way of automatically determining the URL conf.
    router = routers.DefaultRouter()
    router.register(r'users', UserViewSet)
    
    # Wire up our API using automatic URL routing.
    # Additionally, we include login URLs for the browsable API.
    urlpatterns = [
        path('', include(router.urls)),
        path('api-auth/', include('rest_framework.urls', namespace='rest_framework'))
    ]
    ```
#
- Step 7
##### You can now open the API in your browser at http://127.0.0.1:8000/, and view your new 'users' API. If you use the login control in the top right corner you'll also be able to add, create and delete users from the system.

#
![2.gif](../assets/gifts/2.gif)