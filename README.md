***EXPLANATION - SCIENTIFIC GRAPHING CALCULATOR***

***How to write my program?***

1. I will import ***cmath, numpy as np & matplotlib.pyplot as plt*** 

2. I want to define the code being used for plotting a graph with any kind of polynomial given. 

***def plot_polynomial_graph():*** 

3. Under this piece of code, I will ask the user to give me a polynomial equation using x. 

***equation = input("Enter a polynomial equation using x: ")*** 

4. Then I will generate the values for x by using the function called np.linspace. 

  ***x = np.linspace(-10, 10, 400)*** 

5. Now I will try to parse and evaluate the equation using the eval ( ) function. 

***try:***     
  ***y = eval(equation, {'x': x})***

6. After this, I will ask if they want to graph a linear line and then I will plot for the x & y values, the title of the graph and the expected invalid input. 

***user = input("Do you need a linear line?")***     
***if user == "yes":***       
  ***linear = input("Give me the linear expression, ex) 3*x+2!")***       
  ***y2 = eval(linear)***       
  ***plt.plot(x,y2)***

***plt.plot(x, y)***      
***plt.xlabel('X')***     
***plt.ylabel('Y')***     
***plt.grid(True)***

***plt.title("Graph of " + equation)***     
***plt.show()***

***except:***     
  ***print("Invalid input, please try again!")***

7. Moving on, I will be defining the trigonometric graph which would include sin, cos and tan. 

***def plot_trig_graph():*** 

8. Then I will ask the user for a customized trigonometric equation and then I will extract its components. 

***expression = input("Give me a customed equation (ex. 'sin(2x) + 1'): ").split("(")***   
***expression2 = expression[1].split(")")***  
***inside_parentheses = expression2[0]***

9. Then I will be extracting the k term from the expression or equation by setting its value to zero. 

***if len(expression2[1]) == 0:***     
  ***k = 0***   
***else:***     
  ***k = float(expression2[1])***   
***expression = expression[0]***

10. Then I will check if there is any value for term a and if so we will find it as we would have to extract for it.  

***if expression.find("*") != -1:***     
  ***expression = expression.split("*")***     
  ***a = float(expression[0])***     
  ***operation = expression[1]***   
***else:***     
  ***a = 1***     
  ***operation = expression***

11. Then I will be parsing and splitting for both the b & h from the expression which is inside the parenthesis.

***inside_parentheses = inside_parentheses.split("x")***   
***if len(inside_parentheses[0]) == 0:***     
  ***b = 1***   
***else:***     
  ***b = float(inside_parentheses[0])***  
***if len(inside_parentheses[1]) == 0:***     
  ***h = 0***   
***else:***     
  ***h = float(inside_parentheses[1]) / b***
 
12. Then I will generate the x and y values by using the equation that allows me to graph for sin, cos and tan. 

***x = np.linspace(-10, 10, 400)*** 

***if operation == 'sin':***    
  ***y = a * np.sin(b * (x + h)) + k***     
  ***function_name = "Sine"***    
***elif operation == 'cos':***    
  ***y = a * np.cos(b * (x + h)) + k***     
  ***function_name = "Cosine"***    
***elif operation == 'tan':***     
  ***y = a * np.tan(b * (x + h)) + k***     
  ***function_name = "Tangent"***      

  ***y[:-1][abs(np.diff(y)) > 10] = np.nan***

13. Then I will be plotting for the x and y values which have been calculated using the equation. 

***plt.plot(x, y)***     
***plt.title(f"{function_name} Graph")***     
***plt.xlabel("x")***     
***plt.ylabel("y")***     
***plt.grid(True)***     
***plt.show()***

14. Now moving on, I will be defining the quadratic as well as the linear graph together. 

***def quadratic_linear_graph():*** 

15. Then I will be finding the point of intersection between a linear and quadratic graph. 

***a = float(input("Enter coefficient A for quadratic: "))***   
***b = float(input("Enter coefficient B for quadratic: "))***  
***c = float(input("Enter coefficient C for quadratic: "))***   
***quadratic_discriminant = (b**2) - (4*a*c)***

16. Then I will be determining the roots for the quadratic equation. 

***if quadratic_discriminant > 0:***     
  ***root1 = (-b + cmath.sqrt(quadratic_discriminant)) / (2*a)***    
  ***root2 = (-b - cmath.sqrt(quadratic_discriminant)) / (2*a)***     
  ***print("The roots are:", root1, "and", root2)***   
***elif quadratic_discriminant == 0:***     
  ***root1 = -b / (2*a)***     
  ***print("The roots are:", root1)***   
***else:***     
  ***print("There are no real roots")***

17. Now I will make the linear equation equals to the quadratic equations and then solve for x. 

***d = float(input("Enter coefficient D for linear: "))***   
***e = float(input("Enter coefficient E for linear: "))***     
***linear_discriminant** = (b-d)**2-4*a*(c-e)***

18. Then I will determine the point of intersection so it could plot the linear line on the graph. 

***if linear_discriminant > 0:***     
  ***xpoi1 = (-(b - d) + cmath.sqrt(linear_discriminant)) / (2*a)***     
  ***ypoi1 = xpoi1 * d + e***     
  **xpoi2 = (-(b - d) - cmath.sqrt(linear_discriminant)) / (2*a)***     
  ***ypoi2 = xpoi2 * d + e***     
  ***plt.scatter([xpoi1.real, xpoi2.real], [ypoi1.real, ypoi2.real], color='red')***   
***elif linear_discriminant == 0:***     
  ***xpoi1 = -(b - d) / (2*a)***     
  ***ypoi1 = xpoi1 * d + e***     
  ***plt.scatter([xpoi1.real], [ypoi1.real], color='red')***   
***else:***     
  ***print("There are no POI")***

19. Then I will determine both the x and y axis on the graph. 

***x = np.linspace(-10, 10, 100)***   
***y_quadratic = a * x**2 + b * x + c***   
***y_linear = d * x + e***   
***plt.plot(x, y_quadratic)***   
***plt.plot(x, y_linear)***   
***plt.xlabel('X Values')***   
***plt.ylabel('Y Values')***   
***plt.grid(True)***   
***plt.title("Quadratic Equation Graph")***   
***plt.show()***

20. Then I will move onto defining the calculation of the area of each shape.

***def triangle_area():***     
  ***a = int(input("Give me a base: "))***     
  ***b = int(input("Give me a height: "))***     
  ***area = 1/2 * a * b***     
  ***print(area)***    
***def square_area():***     
  ***a = int(input("Give me a number: "))***     
  ***area = a**2***     
  ***print(area)***    
***def rectangle_area():***     
  ***a = int(input("Give me a number: "))***     
  ***b = int(input("Give me another number: "))***     
  ***area = a * b***     
  ***print(area)***    
***def circle_area():***     
  ***pi = 22/7***     
  ***r = int(input("Give me the radius: "))***     
  ***area = pi * r**2***     
  ***print(area)***

21. Now I will be determining the basic calculation for each particular input the user enters. Ex) Addition 

***def area_calculation():***

***choice = input("What operation do you want to do, (addition, subtraction,division, multiplication)? ")***

***if choice == "addition":***     
  ***addition()***   
***elif choice == "subtraction":***     
  ***subtraction()***   
***elif choice == "multiplication":***     
  ***multiplication()***   
***elif choice == "division":***     
  ***division()***

22. Finally, I will be asking the user input for what task they want to choose and then based on that it will go through that particular operation. For example, if I choose option number 1 then it will go through the operation of plotting the polynomial graph and if I choose option 2, then it will plot the trigonometry graph. 

***print("1. Plotting a graph with a polynomial, ex) 3*x**2+4*x+6")*** 
***print("2. Plotting a graph with trig functions, ex) 3*tan(2x+7)-4")*** 
***print("3. Finding the point of intersection between linear and quadratic graph")*** 
***print("4. Finding the area of a triangle, square, rectangle and circle")*** 
***print("5. Performing tasks like addition, subtraction, division and multiplication")*** 

***choice = input("What do you want to do (1 - 5)? ")***

***if choice == "1":***   
  ***plot_polynomial_graph()*** 
***elif choice == "2":***   
  ***plot_trig_graph()*** 
***elif choice == "3":***   
  ***quadratic_linear_graph()*** 
***elif choice == "4":***   
  ***area_calculation()*** 
***elif choice == "5":***   
  ***basic_calculation()*** 
***else:***     
  ***print("Error!")***

***References:*** 

https://www.geeksforgeeks.org/eval-in-python/ 

https://www.prepbytes.com/blog/python/python-eval-function/

https://realpython.com/python-namespaces-scope/

https://teamtreehouse.com/community/help-in-exception-handling-in-python

https://stackoverflow.com/questions/48015191/how-to-extrapolate-a-function-based-on-x-y-values 

https://www.studytonight.com/post/trigonometric-function-in-python

https://scikit-learn.org/stable/modules/ensemble.html#histogram-based-gradient-boosting

https://drive.google.com/file/d/12xUWfxyeovyGPuuy7EvnlKW48uVKxESI/view?usp=drive_web

https://stackoverflow.com/questions/14432557/scatter-plot-with-different-text-at-each-data-point 

https://www.programiz.com/python-programming/examples/quadratic-roots 

https://www.toppr.com/guides/python-guide/examples/python-examples/python-program-solve-quadratic-equation/ 

https://www.geeksforgeeks.org/python-program-to-solve-quadratic-equation/

https://stackoverflow.com/questions/15398427/solving-quadratic-equation

https://www.geeksforgeeks.org/data-visualization-using-matplotlib/ 

https://numpy.org/doc/stable/reference/generated/numpy.linspace.html 

https://www.geeksforgeeks.org/solve-linear-equations-using-eval-in-python/ 

https://realpython.com/python-dicts/ 

https://www.programiz.com/python-programming/methods/string/split 

https://www.geeksforgeeks.org/graph-plotting-in-python-set-1/ 

https://stackoverflow.com/questions/60832850/finding-the-intersect-between-a-quadratic-and-line 

https://www.geeksforgeeks.org/python-extract-words-from-given-string/ 

https://stackoverflow.com/questions/62160148/in-python-what-does-this-do-tan-y-1np-difftan-y-0 

https://realpython.com/len-python-function/ 
https://www.w3schools.com/python/ref_func_len.asp 

https://www.freecodecamp.org/news/what-is-len-in-python-how-to-use-the-len-function-to-find-the-length-of-a-string/ 

# Scientific-Graphing-Calculator - ipynb
