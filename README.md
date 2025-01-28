# fireworks
import turtle
import random

# Set up the screen
screen = turtle.Screen()
screen.bgcolor("black")
screen.title("Fireworks Display")

# Create a turtle to draw the fireworks
firework = turtle.Turtle()
firework.speed(0)
firework.hideturtle()

# Function to draw a rose pattern
def draw_rose(x, y, color):
    firework.penup()
    firework.goto(x, y)
    firework.pendown()
    firework.color(color)
    firework.begin_fill()
    for _ in range(36):
        firework.circle(50, steps=6)
        firework.right(10)
    firework.end_fill()

# Function to create random fireworks
def create_fireworks():
    colors = ["red", "yellow", "blue", "green", "purple", "orange", "pink"]
    for _ in range(10):
        x = random.randint(-300, 300)
        y = random.randint(-300, 300)
        color = random.choice(colors)
        draw_rose(x, y, color)

# Run the fireworks display
create_fireworks()

# Keep the window open until clicked
screen.exitonclick()
