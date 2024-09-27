# Book Outlet - Django Project

This project demonstrates the usage of Django models and how to perform basic CRUD operations on a model (`Book`) using the Django ORM. Below are the key commands and steps performed in the project.

## Setup and Migrations

To create migrations and apply them, use the following commands:

```bash
# Make migrations for the models
py manage.py makemigrations

# Apply the migrations to the database
py manage.py migrate

py manage.py shell

from book_outlet.models import Book

# Creating a new Book object
book1 = Book.objects.create(title="ad", author="GG", rating=4, is_bestselling=True)
print(book1)  # Output: ad (4)

Book.objects.all()

# Example output:
<QuerySet [<Book: Harry Potter 2- Prisoner of askbn (4)>, <Book: Akame Ga Kill (3)>, <Book: Wind Breaker (4)>, <Book: Kakushigoto (5)>, <Book: django (5)>, <Book: Abc (3)>, <Book: django (5)>, <Book: abc (2)>, <Book: ad (4)>]>

from django.db.models import Q
Book.objects.filter(Q(rating__lt=3) | Q(is_bestselling=True))
# Output: <QuerySet [<Book: django (5)>, <Book: django (5)>, <Book: abc (2)>, <Book: ad (4)>]>
