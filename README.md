import turtle
import time


def draw_rectangle_prism(t, width, height, depth, color):
    t.fillcolor(color)
    t.begin_fill()

    # Ön yüz
    t.forward(width)
    t.left(90)
    t.forward(height)
    t.left(90)
    t.forward(width)
    t.left(90)
    t.forward(height)
    t.left(90)

    # Sağ yüz
    t.left(45)
    t.forward(depth)
    t.left(45)
    t.forward(height)
    t.left(135)
    t.forward(depth)
    t.left(45)
    t.forward(height)
    t.left(45)

    # Üst yüz
    t.forward(width)
    t.right(135)
    t.forward(depth)
    t.right(45)
    t.forward(width)
    t.end_fill()


def draw_cube(t, size, color):
    draw_rectangle_prism(t, size, size, size, color)


def draw_triangle_prism(t, base, height, depth, color):
    t.fillcolor(color)
    t.begin_fill()

    # Ön yüz
    t.forward(base)
    t.left(120)
    t.forward(height)
    t.left(120)
    t.forward(height)
    t.left(120)

    # Sağ yüz
    t.left(30)
    t.forward(depth)
    t.left(120)
    t.forward(height)
    t.left(60)
    t.forward(depth)
    t.left(150)

    # Üst yüz
    t.forward(base)
    t.right(60)
    t.forward(depth)
    t.right(120)
    t.forward(base)
    t.end_fill()


# Kurulum
screen = turtle.Screen()
screen.bgcolor("black")

t = turtle.Turtle()
t.speed(0)
t.pensize(2)
t.color("white")

# 1. Şekil (Küp)
t.penup()
t.goto(-200, 100)
t.pendown()
draw_cube(t, 100, "red")
time.sleep(2)

# 2. Şekil (Dikdörtgen Prizma)
t.penup()
t.goto(100, 100)
t.pendown()
draw_rectangle_prism(t, 150, 100, 75, "blue")
time.sleep(3)

# 3. Şekil (Üçgen Prizma)
t.penup()
t.goto(-50, -200)
t.pendown()
draw_triangle_prism(t, 150, 100, 100, "green")
time.sleep(4)

t.hideturtle()
screen.mainloop()
