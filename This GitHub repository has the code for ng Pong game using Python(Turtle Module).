#imported turtle module
import turtle


wind = turtle.Screen() #intialize  screen
wind.title("Ping Pong by Omar") #set the window title
wind.bgcolor("black") #set the background color of the window
wind.setup(width=800, height=600) #set the width and height of the window
wind.tracer(0) #stops the window from updating automatically

#paddle1
paddle1= turtle.Turtle() #intializes turtle object
paddle1.speed(0)    #set the speed of the object
paddle1.shape("square") #set the shape of the object
paddle1.color("blue") #set the color of the object
paddle1.shapesize(stretch_wid=5, stretch_len=1) #stretches to meet the size
paddle1.penup() #stops the object from drawing lines
paddle1.goto(-350, 0) #set the position of the object

#paddle2
paddle2= turtle.Turtle()
paddle2.speed(0)
paddle2.shape("square")
paddle2.color("red")
paddle2.shapesize(stretch_wid=5, stretch_len=1)
paddle2.penup()
paddle2.goto(350, 0)

#ball
ball= turtle.Turtle()
ball.speed(0)
ball.shape("square")
ball.color("white")
ball.penup()
ball.goto(0, 0)
ball.dx = 0.3
ball.dy = 0.3

#score
score1 = 0
score2 = 0
score = turtle.Turtle()
score.speed(0)
score.color("white")
score.penup()
score.hideturtle()
score.goto(0,260)
score.write("Player 1: 0 Player 2: 0", align="center", font=("Courier",24, "normal"))
#functions
def paddle1_up():
    y = paddle1.ycor()  #get the y coordinate of the paddle1
    y += 20  #set the y to increase be 20
    paddle1.sety(y)     #set the y of paddle1 to the new coordinate

def paddle1_down():
    y = paddle1.ycor()
    y -= 20 #set the y to decrease be 20
    paddle1.sety(y)

def paddle2_up():
    y = paddle2.ycor()
    y += 20
    paddle2.sety(y)

def paddle2_down():
    y = paddle2.ycor()
    y -= 20
    paddle2.sety(y)

#keyboard bindings
wind.listen() #tell the window to expect keyboard input
wind.onkeypress(paddle1_up, "w") #when pressing w the function paddle1 is invoked
wind.onkeypress(paddle1_down, "s")
wind.onkeypress(paddle2_up, "Up")
wind.onkeypress(paddle2_down, "Down")
#main game loop
while True:
    wind.update() #updates the screen everytime the loop run
    
    #move the ball
    ball.setx(ball.xcor()+ ball.dx) #ball starts at 0 and every loop runs--- +.5 xaxis
    ball.sety(ball.ycor()+ ball.dy) #ball starts at 0 and every loop runs--- +.5 yaxis

    #border check, top border +300 px, bottom border -300px, ball is 20px
    if ball.ycor() >290: #if ball is at top border
        ball.sety(290) #set y coordinate +290
        ball.dy *= -1 #reverse direction, making +.5---->-.5

    if ball.ycor() <-290:#if the ball at bottom border
        ball.sety(-290)
        ball.dy *= -1

    if ball.xcor() >390: #if the ball at right border
        ball.goto(0,0) #return ball to center 
        ball.dx *= -1 #reverse the x direction
        score1 += 1
        score.clear()
        score.write("Player 1: {} Player 2: {}".format(score1, score2), align="center", font=("Courier",24, "normal"))

    if ball.xcor() <-390: #if the ball at left border
        ball.goto(0,0)
        ball.dx *= -1
        score2 += 1
        score.clear()
        score.write("Player 1: {} Player 2: {}".format(score1, score2), align="center", font=("Courier",24, "normal"))

    #ball and paddle collision
    if (ball.xcor() > 340 and ball.xcor() < 350) and (ball.ycor()< paddle2.ycor() +40 and ball.ycor()>paddle2.ycor() -40):
        ball.setx(340)
        ball.dx *= -1

    if (ball.xcor() < -340 and ball.xcor() > -350) and (ball.ycor()< paddle1.ycor() +40 and ball.ycor()>paddle1.ycor() -40):
        ball.setx(-340)
        ball.dx *= -1
