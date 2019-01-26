# Project: **Magic eight ball**

### Writing the code

##### (Sec. 2) Main program code

Before we start coding, we'll explain a bit what's going on in Sec. 2.

In this part of the code, we'll sense if the user has shaken the Sense HAT.
If the user shakes it, the program should display one of the answers we made
up in the previous section by random.

*Code explanation:* If we look at the skeleton code, we see that the section is within a *while*-loop.
Remember that code inside a while loop runs again and again, until we tell it to
stop. The reason why we want our program to be in a loop is because we want
to continually check if the user has shaken the device.

Because the code is in the *while*-loop, remember that you have to add
a *Tab* at every line, to make it indented. Like this:

```python
while True:
    # write your code like this,
    # with a tab at the start of the line.
```

##### (Sec. 2.1) Check if the user shaken the Sense HAT)

**This part is a bit complicated, so pay attention! Don't be afraid to ask a supervisor if you don't understand something.**

To see if the user has shaken the Sense HAT, we'll have to use the *accelerometer* inside the device. The
accelerometer basically tells us how fast the device is accelerating.

If you don't know what the word *acceleration* means, the next bit will give
you a short lesson in physics.

> **Acceleration:**<br>
>  If *speed* is how fast
> something is moving, *acceleration* is how fast the speed is changing. For example,
> let's say you drop a ball from a cliff. At first, when you first drop the ball,
> its speed is 0 (it's not moving). But due to gravity, it'll *accelerate* and
> gain speed. By the time the ball has reached the ground, it's gained a lot of
> speed.

To get the information from the accelerator, use the following code:

```python
ac = sense.get_accelerometer_raw()
x = ac["x"]
y = ac["y"]
z = ac["z"]
```

Now, in the *x*, *y* and *z* variables, we have information recorded by
the accelerometer. This is all a bit complicated, but the basic gist of it
is this, calculate this:

```python
shake = x*x + y*y + z*z
```

We have stored *x times x plus y times y plus z times z* into the variable *shake*. Now, the larger the variable *shake* is, the more has the Sense HAT been shaken.
We're going to say that if *shake* is *larger* than *5*, the Sense HAT has been shaken. To do this, you're going to have to use an *if*-statement.

If you have detected that the Sense HAT has been shaken (in other words, if
*shake* is larger than 5) you want to display a one of the messages we
wrote earlier by random. To do this, we use the *random.choice* function, like this:

```python
random_message = random.choice(answers)
```

To then display the message stored in *random_message*, we use the functions
*sense.show_message*. Check the *Function Reference* to see how to use it.

This might seem complicated, but it's fairly straightforward. If something confuses
you, ask a supervisor for help.

To break it down, what you need to do is this:

- Get the accelerometer information.
- Calculate *shake*, as shown above.
- If *shake* is greater than 5, show a random message.

--- 

#### [next section --->](section_4.md)
#### [<--- previous section](section_2.md)
