Simple Grocery Store API

This API applictaion is made in tandem with Udemy training: "Postman: The Complete Guide - REST API TEsting".
The purpose of this Api is to place an order which will be ready for pick-up in the store.

The API is available at https://simple-grocery-store-api.glitch.me/

### Endpoints

## **Status**

GET /status
  -  returns the status of the API. Status UP indicates that the API is running as expected.
    ![image](https://github.com/user-attachments/assets/e4771fc2-a09f-4d37-b397-dd9e45c3d230)
- status code $${\color{greenyellow}200 \space OK}$$ indicates a successful response

## **Products**

 GET /products
 
   -  returns a list with all available products
    ![image](https://github.com/user-attachments/assets/c5bb32ac-39b5-4614-b96b-395f1c079518)
  - in API we can work with query parameters (which are case-sensitive) in order to have returned a list of specific products
    ![image](https://github.com/user-attachments/assets/610087f5-031a-46e4-bdd4-5c399d76e52e)
  - based on Note 2, if we create a parameter "name" and make a request we can notice that there are no changes in the response since "name" is not an accepted parameter.



  Note**
1. Storing configuration in collection variables - variables are used to store the configurations
     - https://simple-grocery-store-api.glitch.me was saved in a variable {{baseUrl}}
2. Based on API documentation we can see that parameters accepted by API are: category, results, available. 
