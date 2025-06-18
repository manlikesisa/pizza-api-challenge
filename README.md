 Pizza API Challenge

A RESTful Flask API for managing restaurants, pizzas, and their relationships.

---

 Setup

1. Clone the repo:
  bash
   git clone https://github.com/your-username/pizza-api-challenge.git
   cd pizza-api-challenge
Install dependencies:

bash
Copy
Edit
pipenv install flask flask_sqlalchemy flask_migrate
pipenv shell
Set environment:

bash
Copy
Edit
export FLASK_APP=server/app.py
export FLASK_ENV=development

 Database:
Run these in order:

bash
Copy
Edit
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
python server/seed.py

Routes:
Method	Endpoint	Description
GET	/restaurants	List all restaurants
GET	/restaurants/<int:id>	Show one restaurant + pizzas
DELETE	/restaurants/<int:id>	Delete a restaurant
GET	/pizzas	List all pizzas
POST	/restaurant_pizzas	Add pizza to a restaurant

Postman Testing
Open Postman

Click Import → upload challenge-1-pizzas.postman_collection.json

Test the routes by sending requests

 Validations
price in RestaurantPizza must be between 1–30

Deleting a restaurant also deletes its related RestaurantPizzas

Structure (MVC)
arduino
Copy
Edit
server/
├── app.py
├── config.py
├── seed.py
├── models/
│   ├── restaurant.py
│   ├── pizza.py
│   └── restaurant_pizza.py
├── controllers/
│   ├── restaurant_controller.py
│   ├── pizza_controller.py
│   └── restaurant_pizza_controller.py

 Author:
Clinton Sisa — GitHub