# Django REST-based Authentication

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

1. Run the server:

    ```sh
    (venv)$ python manage.py runserver
    ```
   
1. Your authentication API is now accessible at [http://localhost:8000/api/auth/](http://localhost:8000/api/auth/).
