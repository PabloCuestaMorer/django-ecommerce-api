# E-Commerce API Overview

This GitHub repository contains the code for an E-commerce API developed using **Django** and **Django Rest Framework (DRF)**. The API allows users to interact with an e-commerce system, enabling them to view and create items, place orders, and retrieve order details. It also includes authentication using **token-based authentication** to ensure that certain endpoints are accessible only to authenticated users.

## Project Structure

The project is structured as follows:

- **Core App**: Contains a contact endpoint and basic model serializers. It serves as a foundation for the e-commerce app.
- **E-Commerce App**: Implements the main functionality of the e-commerce API, including item and order endpoints with proper permissions and serializer classes.

## Principal Endpoints

1. **Item Endpoint**:
   - URL: `/api/items/`
   - HTTP Methods: GET (Retrieve all items), POST (Create a new item)
   - Authentication Required: Yes (Token-based)
   - Description: The item endpoint allows users to view all items or create new items in the e-commerce system. Only authenticated users can access this endpoint.

2. **Single Item Endpoint**:
   - URL: `/api/items/<UUID>/`
   - HTTP Methods: GET (Retrieve a single item), PUT (Update a single item), DELETE (Delete a single item)
   - Authentication Required: Yes (Token-based)
   - Description: This endpoint allows users to retrieve, update, or delete a specific item by providing its UUID in the URL. Authentication is required to access this endpoint.

3. **Order Endpoint**:
   - URL: `/api/orders/`
   - HTTP Methods: GET (Retrieve all orders), POST (Place a new order)
   - Authentication Required: Yes (Token-based)
   - Description: The order endpoint enables users to view all orders or place new orders in the e-commerce system. Only authenticated users can access this endpoint.

4. **Single Order Endpoint**:
   - URL: `/api/orders/<UUID>/`
   - HTTP Methods: GET (Retrieve a single order)
   - Authentication Required: Yes (Token-based)
   - Description: This endpoint allows users to retrieve details of a specific order by providing its UUID in the URL. Authentication is required to access this endpoint.

## Important Commands

- **Running the Server**: To run the Django development server, navigate to the project root directory and execute the command `python manage.py runserver`. The API will be accessible at `http://localhost:8000`.

- **Creating Superuser**: To create a superuser (admin) for the Django admin interface, use the command `python manage.py createsuperuser`. Follow the prompts to set the admin username and password.

- **Running Tests**: To execute the unit tests for both the core and e-commerce apps, use the command `python manage.py test`. The tests ensure that the endpoints and models are functioning correctly.

## Django administration
http://localhost:8000/admin/

## API endpoints

- This retrieves the auth token for your_username:

     ```
     http post http://api:8000/api-token-auth/ username=your_username password=your_password
     ```

- This will retrieve all items
     
     ```
     http http://api:8000/item/ 'Authorization: Token your_token'
     ```

- This will retreive a single item
  
     ```
     http http://api:8000/item/**your_item_uuid**/ 'Authorization: Token your_token'
     ```

- This retrieve all orders
  
     ```
     http http://api:8000/order/ 'Authorization: Token your_token'
     ```
  
- This will place an order for item id = your_item_uuid quantity = 1
  
     ```
     http http://api:8000/order/ 'Authorization: Token your_token' item="your_item_uuid" 
     quantity="1"
     ```
 
- This get order id = your_order_uuid
  
     ```
     http http://api:8000/order/**your_order_uuid**/ 'Authorization: Token your_token'
     ```
 
- This will create a contact request
  
     ```
     http http://api:8000/contact/ name="Bobby Stearman" message="test" email="bobby@didcoding.com"
     ```

## Conclusion

This E-commerce API project serves as a foundation for building more complex e-commerce applications. It demonstrates the implementation of token-based authentication, viewsets, serializers, and permission classes in Django Rest Framework. The project can be expanded and customized to suit specific e-commerce business requirements. Feel free to explore the code, run tests, and adapt it to your needs. If you have any questions or feedback, please leave a comment or open an issue in this repository.

Thank you for using this E-commerce API! Happy coding!
