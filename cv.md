# Yauhen Masalkou
## Contacts
* **Email:** haslem11@gmail.com
* **Discord:** eugene#4102
* **LinkedIn:** [eugene-masalkou](https://www.linkedin.com/in/eugene-masalkou-94501a135)
## Info
QA Engineer who wants to learn more about FE
## Skills
* Java
* Junit5
* Selenium
* Postman
* Git
* Python
## Code example
```
from selenium import webdriver
from behave import *

driver = webdriver.Chrome()
driver.maximize_window()


@given('there is Avast SecureLine page in {lang}')
def open_url(context, lang):
	#construct url
	url = 'https://www.avast.com/' + lang + '/lp-business-aff-secureline-45'
	driver.get(url)

	#assure that 1 year 5 PC is checked
	radio_buttons = driver.find_elements_by_class_name('smb-abox_input-group')
	radio_buttons[0].click()

	#get the price
	page_price = driver.find_element_by_class_name('smb-abox_price_discounted')
	#delete spaces between currency sign and price
	context.page_price = page_price.text.replace(" ", "")


@when('buy 1 Year 5 PCs')
def buy(context):
	#scroll and click 'buy now' button
	driver.execute_script("window.scrollTo(0, 300)")
	buy_now = driver.find_element_by_css_selector('.button.orange').click()


@then('price in cart is the same as on {lang} SecureLine page')
def cart_price(context, lang):
	#check language version and get the price in the cart
	if lang == 'pt-br':
		cart_price = driver.find_element_by_class_name('av_streetPrice')
	else:
		cart_price = driver.find_element_by_class_name('av_lineItem-listPrice')
		
	context.cart_price = cart_price.text.replace(" ", "")

	#compare price on web page and in the cart
	assert context.page_price == context.cart_price
```

## Experience
4 years in QA role
## Courses
* [HTML, CSS and JavaScript](https://www.coursera.org/account/accomplishments/certificate/2RXEGUP4E93Q)
* [Front-End Web UI Frameworks and Tools](https://www.coursera.org/account/accomplishments/certificate/ZD4HX68F82F5)
* [Front-End JavaScript Frameworks: AngularJS](https://www.coursera.org/account/accomplishments/certificate/PNHDRSUHU3HT)
## Foreign languages
* English - B2
* Czech - B2
