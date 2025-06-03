Simple Grocery Store API

This API applictaion is made in tandem with Udemy training: "Postman: The Complete Guide - REST API TEsting".
The purpose of this Api is to place an order which will be ready for pick-up in the store.

The API is available at https://simple-grocery-store-api.glitch.me/

### Endpoints

## **Status**

GET /status
  -  returns the status of the API. Status UP indicates that the API is running as expected.
    ![image](https://github.com/user-attachments/assets/e4771fc2-a09f-4d37-b397-dd9e45c3d230)
  - status code $$\color{greenyellow}{200 \space OK}$$ indicates a successful response

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

    
  Note**
1. Storing configuration in collection variables - variables are used to store the configurations
     - https://simple-grocery-store-api.glitch.me was saved in a variable {{baseUrl}}
2. Based on API documentation we can see that parameters accepted by API are: category, results, available. 
