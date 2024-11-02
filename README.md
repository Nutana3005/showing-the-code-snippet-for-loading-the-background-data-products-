# showing-the-code-snippet-for-loading-the-background-data-products-
from behave import given
from app.models import Product

@given("the following products")
def step_impl(context):
    for row in context.table:
        Product.create(name=row['name'], category=row['category'], available=row['available'])
