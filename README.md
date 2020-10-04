### Installation on linux
- Configure .env file
- Run the following command to load dipendencies:
```bash 
    composer install 		# dependencies
    php artisan jwt:secret 	# set auth secret
    php artisan migrate 	# populate database tables
```

- Run ```php artisan serve```
> Error PDOException::("could not find driver")
> ```bash 
>   sudo nano /etc/php/php.ini
>   uncomment the row ;extension=pdo_mysql
> ```
> 

### API

- ```POST /api/register``` –> Create user 

    ```json
    {
    	"name" : "test",
    	"email" : "test@gmail.com",
    	"password" : "test123",
    	"password_confirmation" : "test123"
    }
     ```     
- ```POST /api/authenticate``` –> with email and password, obtain a JWT token
    ```json
    {
    	"email" : "test@gmail.com",
    	"password" : "secret"
    }
    ```
- ```GET /api/user``` –> Get user info, remember that JWT requires the token as a header.
