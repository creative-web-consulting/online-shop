# online-shop

##### Install RabbitMQ in your machine
If you are using Linux, you can install RabbitMQ from the shell using the following 
command:

```
    apt-get install rabbitmq
```
If you need to install RabbitMQ on macOS or Windows, you can find standalone 
versions at https://www.rabbitmq.com/download.html. On this site, you can also 
find detailed installation guides for different Linux distributions, other operating 
systems, and containers.
After installing it, launch RabbitMQ using the following command from the shell:

```
    rabbitmq-server
```

##### Open another shell and start the Celery worker from your project directory with the following command:
```
    celery -A <your-project-name-here> worker -l info
```

##### Open one more shell and start the development server with this command:
``` 
    python manage.py runserver
```

##### To monitor the asynchronous tasks that are executed:
```
    celery -A <your-project-name-here> flower
```

Then open http://localhost:5555/dashboard in your browser. You will be able to see the active Celery workers and asynchronous task statistics.

##### Change the followings variables in the settings.py file for sending emails via Gmail servers using a Google account:
    - EMAIL_HOST_USER = 'your-host-user'
    - EMAIL_HOST_PASSWORD = 'your-email-password'

##### Create a Braintree sandbox account:
1. Open *https://www.braintreepayments.com/sandbox* in your browser
2. Fill in the details to [create a new sandbox account](https://www.braintreepayments.com/sandbox)
3. You will receive an e-mail from Braintree with a link
4. Follow the link and complete your account setup
5. Once you are done, log in at _https://sandbox.braintreegateway.com/login_. 
6. Your **merchant ID** and __public/private keys__ will be displayed.
7. Change the following settings to the settings.py file of your project:
    - BRAINTREE_MERCHANT_ID = 'Your merchant ID here' 
    - BRAINTREE_PUBLIC_KEY = 'Your Public Key here'
    - BRAINTREE_PRIVATE_KEY = 'Your Private Key here' 


Run the following command as well to copy all static files from your applications into the 
directory defined in the STATIC_ROOT setting. This allows each application to provide 
its own static files using a static/ directory containing them:

```
    python manage.py collectstatic
```

*This project also requires installing WeasyPrint's dependencies for your operating system from https://weasyprint.readthedocs.io/en/latest/install.html*


