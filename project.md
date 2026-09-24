    from turtle import Screen, Turtle, tracer, done
    from colorsys import hsv_to_rgb
    from random import uniform
    from time import sleep


    def setup_screen():
        screen = Screen()
        screen.bgcolor("black")
        screen.title("star spiral animation")
        tracer(2)
        return screen


    def create_turtle():
        t = Turtle()
        t.speed(0)
        t.hideturtle()
        return t


    def draw_spiral(t, steps=300, angle=147, hue_step=0.005):
        hue = uniform(0, 1)  # random starting color each run
        for i in range(steps):
            color = hsv_to_rgb(hue, 1, 1)
            t.pencolor(color)
            t.forward(i * 3)
            t.right(angle)
            hue += hue_step


    def write_title(t, text="PYTHONKING"):
        t.up()
        t.goto(0, -360)
        t.color("white")
        t.write(text, align="center", font=("Arial", 24, "bold"))


    def main():
        screen = setup_screen()
        t = create_turtle()
        draw_spiral(t)
        screen.update()
        sleep(1)  # short pause before the title appears
        write_title(t)
        screen.update()
        done()


if __name__ == "__main__":
    main()# project
