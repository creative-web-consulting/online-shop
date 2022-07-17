# online-shop

##### Install RabbitMQ in your machine

##### Open a shell and run RabbitMQ with the following command:
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


