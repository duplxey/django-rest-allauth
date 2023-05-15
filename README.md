# Django REST-based Authentication

The repository is split into two branches:

1. `master` -- basic authentication + social authentication
2. `basic` -- basic authentication only

If you do not wish to use social authentication make sure to switch to the `basic` branch.

## Want to learn how to build this?

Check out the [post](#).

## Want to use this project?

1. Fork/Clone

1. Create and activate a virtual environment:

    ```sh
    $ python3 -m venv venv && source venv/bin/activate
    ```

1. Install the requirements:

    ```sh
    (venv)$ pip install -r requirements.txt
    ```

1. Apply the migrations:

    ```sh
    (venv)$ python manage.py migrate
    ```

1. Enter your SMTP settings in *core/settings.py* file:

    ```python
    EMAIL_BACKEND = "django.core.mail.backends.smtp.EmailBackend"
    EMAIL_HOST = "<your email host>"
    EMAIL_USE_TLS = False
    EMAIL_PORT = "<your email port>"
    EMAIL_HOST_USER = "<your email user>"
    EMAIL_HOST_PASSWORD = "<your email password>"
    DEFAULT_FROM_EMAIL = "<your default from email>"
    ```

1. Register your app on Google and take note of your client ID and secret. 

1. Enter the client IDs and secrets in *core/settings.py* respectively:

   ```python
   SOCIALACCOUNT_PROVIDERS = {
       "google": {
           "APP": {
               "client_id": "<your google client id>",
               "secret": "<your google secret>",
               "key": "",  # leave empty
           },
           "SCOPE": [
               "profile",
               "email",
           ],
           "AUTH_PARAMS": {
               "access_type": "online",
           },
           "VERIFIED_EMAIL": True,
       }
   }
   ```

1. Run the server:

    ```sh
    (venv)$ python manage.py runserver
    ```
   
1. Your authentication API is now accessible at [http://localhost:8000/api/auth/](http://localhost:8000/api/auth/).
