# Python-Final-
CSCI 220 

Test 2
a.	“te”
b.	[“1”, “test”, “2”, “day”]
c.	test[0] * 3 = ‘111’
d.	len(text) = 12
e.	text[0]+ text[7]= “12”
f.	text[:3] + text[9:] = ‘1 tday’
2. values = [“there”, 3, “9 ”, “hello”, 25]
a.	values[3] + values[0]
b.	values[4] * values[1]
c.	int(values[2]) + values[1]
d.	values[3]* values[4]
e.	values[1:3] +values[4:]
f.	len(values)
3. address= “529 W Wimbledon Drive,Charleston SC,29412”
a.	address.split(“,”)
    print(address.split(‘,’)[2])
   b. address.split(‘,’)[1].split()
   c. address.upper()
4. 
def subtract(a, b):
    return a - b
def main():
    print(‘testing test 2 functions’’)
    print(‘testing subtract’)
    print(‘/Expected: 6, ‘actual’,  subtract(9-3)’)
main()

5. 
6. 
stringLen = 0 
for char in text:
    stringLen+= 1
print (stringLen)

7. 
def joinFirst(string_List):
    result= ‘’
    for string in string_List:
    result += string[0]
    return result 

8.def username(full_name):
    full_name.lower().split()
first_name= name_list[0]
middlename= name-list[1]
lastname= name_list[2]
result= last_name [:5] + first_name[:3] + str(len(middle_name))
return result 
print(username(Elizabeth Jean Taylor))

9.
input_file= open(‘data.txt’, ‘r’)
output_file= (“average.txt”, ‘w’)
for line in input_file:
    data= line.split()
    first_name= data[0]
    last_name= data[1]
    grades= data[2:]
    total = 0
    for grade in grades:
        grade = eval(grade)
        total+= grade
    average = total / len(grades)
    output_file,write(last_name + ‘, ‘ + first_name[0] + ‘.:’ + str(average) ‘\n’)
input_file.close()
output_file.close()

10. 
def distance(a,b)
    dx= b.getX() - a.getX()
    dy= b.getY() - a.getY()
    distance= math.sqrt(dx**2 + dy**2)
return distance 

11. win = GraphWin(“circle” , 200, 300)
radius= 30
win.getMouse()
circle= Circle(Point(winwidth/2, winheight/2, raidus))
circle.draw()win
win.close()



Name Answer Key
Computer Science 220
Test 3
April 20, 2015

1.	Apply deMorgan’s law to the following:
a.	not(x >= 12)    	x < 12
b.	not(y < 15)   	x >= 15
c.	not (x == 3 or y <= 5)   	x != 3 and y > 5
d.	not(x  != 8 and z  >  4)   	x == 8 and z <= 4
e.	not(x >=5 or y == 2 and z < 0)	 x < 5 and y != 2 or z >= 0

2.	 Assume a function,  distance(pt1, pt2) → float , exists that accepts two Point objects and returns the Euclidean distance between these points.   Write a function equidistant(ptA, ptB, ptC, ptD) → Boolean that accepts four  Point objects and returns  True if the distance between ptA and ptB is the same as the distance between ptC and ptD  and False if they are not.  

def equidistant(a, b, c, d):
	return distance(a, b) == distance(c, d)

3.	Write a function cellCount(wbc, rbc) → String segment that will help a doctor diagnosis a patient based on their white and red blood cell counts.  The function will accept two variables, wbc and rbc, which are numeric variables.  It should return the appropriate string (“Normal”, “Low”, “High”) based on the chart below.  It should favor alerting people of a high result over a low result thus a person with wbc of 12000 and a rbc of 2.5 would get the message returned of “High”.

	WBC Range	RBC	Result
Both are true:	4500 – 11000	3.5 - 5	Normal
Either are true:	Lower than 4500	lower than 3.5	Too low
Either are true:	Higher than 11000	higher than 5	Too high
 
def cellCount(wbc, rbc):
	if wbc < 4500 or rbc < 3.5:
		return "Too low"
	elif wbc >= 11000 or rbc >= 5:
		return "Too high"
	else:
		return "Normal"

4.	Write a code segment that continuously asks a user to enter a new password until he/she enters a valid password.  After it is entered, print the valid password to the screen.  Valid passwords have a length of 8 to 14 characters and cannot begin with the * character.  

	while True:
		password = input("Password: ")
		length = len(password)
		if length >= 8 and length <= 14 and password[0] != '*':
			break
	print("Password:", password)

5.	Write a function legitValuePosition(nums)→ pos that  accepts a list of numbers  and returns an integer representing a list position.  The function should search the list to find a number that is greater than 50 and no more than 100.  It should return the position of the first such number in the list.  If the list does not contain a legitimate value, the function should return -1.  


def legitValuePosition(nums):
	for i in range(len(nums)):
		num = nums[i]
		if num > 50 and num <= 100:
			return i
	return -1

6.	Write a code segment that builds a list of names based on user input.  Allow the user to input a single name at a time until they enter the empty string.  Using list methods, display the names to the user in reverse alphabetical order.

	names = []
	while True:
		name = input("Name:")
		if name == '':
			break
		names.append(name)
	names.sort()
	names.reverse()
	print(names)

7.	Define a class to represent a customer. A customer should be created with an integer id, strings fname and lname. Maintain a list of floats that represent purchase dollar values for the customer. Define methods: addPurchase(purchase) which adds a purchase to the list, avgPurchase which returns the average amount spent by the customer per transaction, and a __str__ method which provides id, name, and the average amount he or she spends. 

class Customer:

	def __init__(self, id, fname, lname):
		self.id = id
		self.fname = fname
		self.lname = lname
		self.purchases = []

	def addPurchase(self, purchase):
		self.purchases.append(purchase)

	def avgPurchase(self):
		total = 0
		for purchase in self.purchases:
			total += purchase
		return total / len(self.purchases)

	def __str__(self):
		return "[" + "Id: " + str(self.id) + ", Name: " + self.fname + " " + self.lname + ", Average purchase: " + str(self.avgPurchase()) + "]"

8.	Python’s index() method on lists throws a ValueError if the argument passed in to index() is not in the list. If the element is in the list, its index is returned. Define your own function indexWithoutException(list, e) that behaves like Python’s index method except that it returns -1 if the search element is not in the list rather than throwing an exception. 

def indexWithoutException(list, e):
	try:
		return list.index(e)
	except ValueError:
		return -1

		* or *

	if e in list:
		return list.index(e)
	else:
		return -1
9.	A BUGGY function is defined for you that uses a linear search to test whether or not an element is in a list. Write a unit test that fails for this implementation and then rewrite the function correctly. 


def is_in_linear_search(mylist, x):
	for element in mylist:
		if element == x:
			return True
		else:
			return False

def test_is_in_linear():
	


	def test_is_in_linear_search(self):
		self.assertEqual(is_in_linear_search(['a', 'b', 'c'], 'b'), True)

another test case:
		self.assertEqual(is_in_linear_search(['a', 'b', 'c'], 'd'), False)

Correct implementation: 
def is_in_linear_search(mylist, x):
	for element in mylist:
		if element == x:
			return True
	return False
