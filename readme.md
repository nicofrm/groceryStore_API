Simple Grocery Store API

This API applictaion is made in tandem with Udemy training: "Postman: The Complete Guide - REST API TEsting".
The purpose of this Api is to place an order which will be ready for pick-up in the store.

The API is available at https://simple-grocery-store-api.glitch.me/

### Endpoints

## **Status**

GET /status
  -  returns the status of the API. Status UP indicates that the API is running as expected.
    ![image](https://github.com/user-attachments/assets/e4771fc2-a09f-4d37-b397-dd9e45c3d230)
  - status code <code style="color : greenyellow">200 OK</code> indicates a successful response
  

## **Products**

 GET /products
 
   -  returns a list with all available products
    ![image](https://github.com/user-attachments/assets/c5bb32ac-39b5-4614-b96b-395f1c079518)
  - in API we can work with query parameters (which are case-sensitive) in order to have returned a list of specific products
    ![image](https://github.com/user-attachments/assets/610087f5-031a-46e4-bdd4-5c399d76e52e)
  - based on Note 2, if we create a parameter "name" and make a request we can notice that there are no changes in the response since "name" is not an accepted parameter.
  - further we will test the respone from API using query parameter "results". According to API documentation "results" is an integer and must be a number between 1 and 20. By default, only 20 products will be displayed.
    
    Case1:
    
    ![image](https://github.com/user-attachments/assets/58b3a2ef-ba91-4c22-9a9b-fe694cc61fdd)
    
    Case2:

    ![image](https://github.com/user-attachments/assets/a495e4aa-6808-41e3-a28a-58a990290898)
    
    Case3:
    
    ![image](https://github.com/user-attachments/assets/0b3aed32-5711-4705-a6ea-73d548f0f151)
    
    Case4:
    
    ![image](https://github.com/user-attachments/assets/24254653-263f-4314-9464-dbdac1ca37d5)
    
    Case5:
    
    ![image](https://github.com/user-attachments/assets/c50a53b0-c249-4706-825e-6738cd9e3375)
    
    Based on the above cases tested, we have identified a few possible bugs which would require immediate reporting to development team. 

### Get a product

GET /products/:productId

![image](https://github.com/user-attachments/assets/4fcb4256-99c6-4744-89bc-38f13fc40007)

  - returns a single product from the inventory, by specifying the productId value at the path variable filed

## **Carts**

### Get a cart

GET /carts/:cartId

![image](https://github.com/user-attachments/assets/dc2e072c-5bca-4cf8-a0bb-cea6eb530e4d)

  - returns a cart

### Get cart items

GET /carts/:cartId/items

![image](https://github.com/user-attachments/assets/4fd18ee7-1dcb-40d8-8bc1-4737ba893965)

  - returns the items in a cart

### Create a new cart

POST /carts

![image](https://github.com/user-attachments/assets/2af32cee-11bd-47da-874d-3fb37bf15d1f)

  - for creating a new cart, a POST request is used
  - creates a new cart and returns the id in the response body.

### Add an item to cart

GET {{baseUrl}}/carts/:cartId/items

![image](https://github.com/user-attachments/assets/65d62920-93ec-4aab-9d94-34c5ee465889)

  - allows the addition of items to an existing cart. Only one item can be added at a time.
  - the request body needs to be in JSON format


## API Authentication

API authentication is the process of verifying the identity of a user or application attempting to access an API. It ensures that only authorized entities can interact with the API's resources, preventing unauthorized access, data breaches, and security vulnerabilities. 


### Register a new API client

POST /api-clients

![image](https://github.com/user-attachments/assets/4133f084-f641-4cc5-932b-fa2345555a48)


  - the request body needs to be in JSON format
  - the response body will contain the access token 
  - status code 201 Created - indicates that the client has been registered successfully
  - staus code 400 Bad Request - indicates that the parameters provided are invalid
  - 409 Conflict - indicated that an API client has already been registered with this email

    
![image](https://github.com/user-attachments/assets/c3db1641-d575-4966-9692-af4f8696b9f6)


  - the access token provided in the response body, needs to be stored in collection variables

### Modify an item in the cart

PATCH /carts/:cartId/items/:itemId

![image](https://github.com/user-attachments/assets/2048b2cd-6a9e-4fd9-9567-e4a520283ae1)


![image](https://github.com/user-attachments/assets/c3691b21-a621-46b8-a77a-e3a0ce929d74)

  - **PATCH** allows modifying information about an existing item from the cart.
    


### Replace an item in the cart 

PUT /carts/:cartId/items/:itemId


![image](https://github.com/user-attachments/assets/0e17bc38-7865-4239-b0a7-56920033d2b0)


![image](https://github.com/user-attachments/assets/acaa8282-20aa-4bdc-9527-5ce9ddb583f8)


  - **PUT** replaces an item in the cart
    
### Delete an item in the cart

DELETE /carts/:cartId/items/:itemId


![image](https://github.com/user-attachments/assets/5caf57df-680e-4a22-9d1d-0691385fdea1)


![image](https://github.com/user-attachments/assets/78d82c30-83fb-4222-9a70-8d0d4babc129)

  - **DELETE** deletes an item from the cart

    

  Note**
1. Storing configuration in collection variables - variables are used to store the configurations
     - https://simple-grocery-store-api.glitch.me was saved in a variable {{baseUrl}}
2. Based on API documentation we can see that parameters accepted by API are: category, results, available.
3. JSON has a key-value format, like "firstName": "Nico". Where "firstName" is the key and "Nico" is the value. 
