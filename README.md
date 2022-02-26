# Python-turtle-2
Making a rocket ship with python turtle



 
######################################################
# <imports>
import turtle
import random
t1 = turtle.Turtle()
t = turtle.Turtle()

list_of_colors = ["Red", "Blue", "Black", "dark green", "indigo", "tan", "White", "dark orange"]
# draw triangle function 
def draw_triangle(t, x, y, length, pen_color, fill_color, heading, pen_size):
  """Draws a triangle of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  
  t.penup()
  t.goto(x, y)
  t.pendown()
  t.setheading(heading)

  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()

  for i in range(3):
    t.forward(length)
    t.left(120)

  if (fill_color != 'None'):
    t.end_fill()
  
# draw square funtion
def draw_square(t, x, y, length, pen_color, fill_color, heading, pen_size):
  """Draws a square of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  
  t.penup()
  t.setheading(heading)
  t.goto(x, y)
  t.pendown()
  
  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()
  for i in range(4):
    t.forward(length)
    t.left(90)
  if (fill_color != 'None'):
    t.end_fill()
  
# draw circle function
def draw_circle(t, x, y, heading, pen_size, pen_color, fill_color, radius, extent, steps):
  """Draws a circle of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  
  t.penup()
  t.goto(x, y)
  t.pendown()
  t.setheading(heading)

  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()
  t.circle(radius, extent = extent, steps = steps)
  
  if (fill_color != 'None'):
    t.end_fill()
  
# draw rectangle function
def draw_rectangle(t, x, y, heading, pen_size, pen_color, fill_color, length, width):
  """Draws a rectangle of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  t.setheading(heading)

  # position
  t.penup()
  t.goto(x, y)
  t.pendown()

  #color
  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()
  
  for i in range(2):
    t.forward(length)
    t.left(90)
    t.forward(width)
    t.left(90)
    print(t.position())

  if (fill_color != 'None'):
    t.end_fill()
    
# draw star function
# it draws a star using draw_circle function
def draw_star(t, x, y, heading, pen_size, pen_color, fill_color, radius, extent, steps):
  """Draws a star of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  
  t.penup()
  t.goto(x, y)
  t.pendown()
  t.setheading(heading)

  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()
  t.circle(radius, extent = extent, steps = steps)
  
  if (fill_color != 'None'):
    t.end_fill()
 
# draw shape
def draw_shape(t, x, y, heading, pen_size, pen_color, fill_color, radius, steps):
  """Draws a Pentagon of any size and any location"""
  t.pensize(pen_size)
  t.pencolor(pen_color)
  
  t.penup()
  t.goto(x, y)
  t.pendown()
  t.setheading(heading)

  if (fill_color != 'None'):
    t.fillcolor(fill_color)
    t.begin_fill()
  t.circle(radius, steps = steps)
  
  if (fill_color != 'None'):
    t.end_fill()

# draw_star(t1, 0, 0, 0, 1, list_of_colors[0], list_of_colors[1], 20, 720, 5 )

def draw_background(t):
  """Draws the background of the turtle that consists of random stars and some other shapes."""
  draw_circle(t, 150, -150, 0, 1, list_of_colors[2], list_of_colors[6], 45, 360,   3)
  x, y = t.position()
  draw_circle(t, 150, -150, 1, 5, list_of_colors[1], list_of_colors[6], 20, 360,   None)
  x, y = t.position()
  draw_shape(t, 150, -170, 0, 1, list_of_colors[0], list_of_colors[2], 20, 5)
  x, y = t.position()
  for i in range(random.randint(20, 30)):
    x = random.randint(-250, 250)
    y = random.randint(-250, 250)
    draw_star(t, x, y, 0, 2, list_of_colors[0], list_of_colors[0], 15, 720, 5)
  x, y = t.position()

def draw_object(t):
  """Draws a rocketship that consists of different shape functions"""
  draw_rectangle(t, -40, -80, 45, 5, list_of_colors[4], list_of_colors[2], 250, 100)
  x, y = t.position()
  draw_triangle(t, 66.07, 167.49, 100, list_of_colors[4], list_of_colors[4], 315, 10)
  x, y = t.position()
  draw_square(t, -70, -10, 25, list_of_colors[1], list_of_colors[1], 45, 3)
  x, y = t.position()
  draw_square(t, -25, -60, 25, list_of_colors[1], list_of_colors[1], 45, 3)
  x, y = t.position()
  draw_square(t, -30, 30, 25, list_of_colors[1], list_of_colors[1], 45, 3)
  x, y = t.position()
  draw_square(t, 20, -10, 25, list_of_colors[1], list_of_colors[1], 45, 3)
  x, y = t.position()
  draw_circle(t, 50, 40, 1, 5, list_of_colors[1], list_of_colors[4], 40, 360,   None)
  x, y = t.position()
  draw_circle(t, 50, 60, 1, 5, list_of_colors[0], list_of_colors[0], 20, 360,   None)
  draw_triangle(t, -49, -79, 50, list_of_colors[0], list_of_colors[0], 135, 10)
  x, y = t.position()
  draw_triangle(t, -68, -62, 60, list_of_colors[0], list_of_colors[0], 135, 10)
  x, y = t.position()
  draw_triangle(t, -78, -51, 50, list_of_colors[0], list_of_colors[0], 135, 10)
  x, y = t.position()
  draw_triangle(t, -70, -95, 50, list_of_colors[7], list_of_colors[7], 135, 10)
  x, y = t.position()
  draw_triangle(t, -96, -66, 50, list_of_colors[7], list_of_colors[7], 135, 10)
  x, y = t.position()
  draw_triangle(t, -98, -91, 50, list_of_colors[7], list_of_colors[7], 135, 10)
  x, y = t.position()
  draw_rectangle(t, -17, -98, 45, 5, list_of_colors[4], list_of_colors[4], 100, 25)
  draw_rectangle(t, -112, -6, 45, 5, list_of_colors[4], list_of_colors[4], 100, 25)

  
def main():
  # <variable declarations> (turtles, screen)>
  """Organizes all the function calls together"""
  s = turtle.Screen()
  s.bgcolor(list_of_colors[2])
  # t = turtle.Turtle()
  t1 = turtle.Turtle()
  t2 = turtle.Turtle()
  s.setup(width = 500, height = 500)
  s.tracer(0)
  
  def show_coord(x, y):
    print(x, y)
  s.onclick(show_coord)

  draw_background(t1)
  draw_object(t2)

  t2.penup()
  t2.goto(-37, -6.0)
  t2.pendown()
  t2.color(list_of_colors[0])
  t2.pensize(10)
  t2.write("NASA")

  print("Samuel Shodiya - 669794692")

main()


## information for scorers

## on what line number is the required for loop?
## Line 159

## on what line number is the required use of a random number?
## Line 160

## on what line number is the required use of a conditional statement?
## Line 33
