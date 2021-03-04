# The Hive Shop (Server)

- Android app version [here](https://github.com/doctor-blue/the-hive-shop)
- Flutter app version [here](https://github.com/doctor-blue/the-hive-shop-flutter)
- React Native version: comming soon.

## Environment
- Python 3
- Pip- với Linux (Distro like Ubuntu or Debian): sudo apt install python3-pip
- Framework Webpy: https://webpy.org/

### To run the server, open project folder and run the file app.py (after you have a complete environment) with the command:
- Win: python app.py
- Linux: python3 app.py
- MacOS: python3 app.py

# Api Documents
## For nomal testing
#### (*) http://your_ip_address/products (GET method)
- Api return something like this:
```json
[
    {
        "id": "0",
        "title": "Vagabond sack",
        "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/0-0.jpg",
        "price": "120",
        "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
    },
    {
        "id": "1",
        "title": "Stella sunglasses",
        "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/1-0.jpg",
        "price": "58",
        "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
    },
    ...
]
```


## For naughty clowns
#### (*) http://your_ip_address/authentication/signin (POST method) - Sign In
- You need to post a json string like this:
```json
 {
    "password": "12345678",
    "address": "",
    "is_male": false,
    "is_admin": true,
    "email": "abcd@gmail.com",
    "date_of_birth": "",
    "phone_number": ""
  }
```
#### (*) http://your_ip_address/authentication/signup (POST method) - Create a account
- You need to post a json string like this:
```json
 {
    "password": "12345678",
    "address": "",
    "is_male": false,
    "is_admin": true,
    "email": "abcd@gmail.com",
    "date_of_birth": "",
    "phone_number": ""
  }
```
#### (*) http://your_ip_address/authentication/signup (POST method) - Update User Profile
- You need to post a json string like this:
```json
  {
    "password": "12345678",
    "address": "Ha Noi",
    "is_male": false,
    "is_admin": true,
    "email": "abcd@gmail.com",
    "date_of_birth": "27-2-2021",
    "phone_number": "0987654321"
  }
```


#### (*) http://your_ip_address/cart (POST method) - Add produdct to card
- You need to post a json string like this:
```json
  {
        "email": "abcde@gmail.com",
        "item": 
            {
                "id": "0",
                "title": "Stella sunglasses",
                "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/1-0.jpg",
                "price": 58.0,
                "description": "description 2",
                "amount": 3
            }
        
  }
```
+ email is user email.
+ Item is mean product in cart and it has "amount" property.

### (*) http://your_ip_address/cart/your_email (GET method) - your_email is mean user email
- Example: http://0.0.0.0:8080/cart/abcd@gmail.com 
- Api return something like this:
```json
{
    "email": "abcd@gmail.com",
    "items": [
        {
            "id": "0",
            "title": "Vagabond sack",
            "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/0-0.jpg",
            "price": 120.0,
            "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
            "amount": 1
        }
    ]
}
```
### (*) http://your_ip_address/cart/your_email (PATCH method) - your_email is mean user email
- Example: http://0.0.0.0:8080/cart/abcd@gmail.com 
- You need to post a json string like this:
```json
  {
        "email": "abcde@gmail.com",
        "item": 
            {
                "id": "0",
                "title": "Stella sunglasses",
                "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/1-0.jpg",
                "price": 58.0,
                "description": "description 2",
                "amount": 3
            }
        
  }
```
### (*) http://your_ip_address/cart/your_email (PUT method) - your_email is mean user email
- Example: http://0.0.0.0:8080/cart/abcd@gmail.com 
- You need to post a json string like this:
```json
  {
        "email": "abcde@gmail.com",
        "item": 
            {
                "id": "0",
                "title": "Stella sunglasses",
                "url": "https://storage.googleapis.com/material-vignettes.appspot.com/image/1-0.jpg",
                "price": 58.0,
                "description": "description 2",
                "amount": 3
            }
        
  }
```
