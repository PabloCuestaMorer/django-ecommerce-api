# python-django-rest-api

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
