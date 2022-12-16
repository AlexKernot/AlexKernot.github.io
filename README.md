<link rel="stylesheet" href="stylesheet.css">

# <strong>Alex Kernot - Portfolio </strong>
---
## **About me:**
I am a self-taught programmer who specialises in C#/C++, and I will be going to university in 2023 for either computer science or software engineering. I have intermediate knowledge in both and have spent the past few years familiarizing myself with the languages after learning Java. I have some knowledge in Python and would be open to learn a new language for a long term and sufficiently interesting project.

My non-coding hobbies are coffee making, photography, reading, and general technology. I like experimenting with unknown features of the camera, like long exposure shooting and HDR for stunning night-time and sunset photos. I also particularly enjoy keeping up to date with the current tech news and exploring its new innovations.

My professional experience primarily comes from volunteering with the SA Country Fire Service. I am on call 24/7 for a wide range of incidences including:
*	Assist and Rescue, involving vehicle accidents, rescue from heights, assisting SAAS, and more.
*	Grass and Structure fires; offensive and defensive fire suppression.
*	Disaster Response; dealing with flooding, lightning, strong winds, and other acts of God.<br />

*While I am on call 24/7, I choose what I respond to and at what times so it will not impact my work responsibilities.*

___
## **Projects:**

### Math
**Language: C#<br />**
**Contribution: Solo project<br />**

With the goal of creating a fully functioning scientific calculator without using standard libraries (Except for console input and output,) this project has required me to learn new skills, algorithms and collaborate to understand unfamiliar math concepts.<br />
-	Process a complex string of calculations while following order of operation rules.<br />
  -	Uses shunting yard and post stack evaluators for interpretation
-	Calculate the basic trigonometric functions through an approximation correct to 12 decimal places
-	Calculate LCM and GCD
-	Basic arithmetic operations including exponentials.

At a glance:
```csharp
// Sine.cs

public static decimal Sin(decimal n, int pow = 11)
{
    if (n > pi || n < -pi)
        // Brings n inside domain {pi > n > -pi}
        n = Functions.Modulo(n + pi, 2 * pi) - pi;

    decimal sinx = 0;
    decimal num = 0;

    for (int i = 0; i < pow; i++)
    {
        // num = -1^i * n^(2i+1) / (2i+1)!
        num = (Functions.Exponents(-1, i) * Functions.Exponents(n, 2 * i + 1)) / (Functions.Factorial(2 * i + 1));
        sinx += num;
    }

    return sinx;
}

// Modulo.cs

public static decimal Modulo(decimal a, decimal b)
{
    b = Functions.Absolute(b);

    // Euclidian modulo: r = a - |b| floor(a/|b|)
    decimal r = a - b * Functions.Floor(a / b);
    return r;
}
```

**See full code at [https://github.com/AlexKernot/Math](https://github.com/AlexKernot/Math)**

### Minesweeper
**Language: C++<br />**
**Contribution: Solo project<br />**

A complete recreation of the classic game Minesweeper, using SFML. This taught me the importance of using minimal memory and how to use pointers and objects to increase the efficiency of operations on multi-dimensional arrays
Capabilities:
-	Timer
-	Bomb counter
-	Flood fill when cascade is activated (revealing a 0 square)
-	Causes cascade on first click of every game
-	Generates new board on demand

At a glance:
```cpp
// RevealSquare

...
// If there is a flag in the square, turn it into a normal block
if (hiddenNumber == 2) {
    gameBoard->setSprite(pointX, pointY, 0, 49, 16, 16);
    gameBoard->setHidden(pointX, pointY, 0);
    gameBoard->incrementBombs();
    return false;
}

// If the number is 0 (black square), Flood fill
if (numberInSquare == 0 && !recursion) {
    gameBoard->addRevealed(FloodFill(gameBoard, pointX, pointY));

    for (int i = 0; i < boardWidth; ++i) {
        for (int j = 0; j < boardHeight; ++j) {
            if (gameBoard->getHidden(i, j) == 1) {
                RevealSquare(gameBoard, (i * 16 * scaleFactor) + leftOffset, (j * 16 * scaleFactor) + topOffset, true);
            }
        }
    }

    if ((boardWidth * boardHeight) - gameBoard->getRevealed() == numBombs) {
        gameBoard->setButton(72, 24, 24, 24);
        cout << "win";
        gameBoard->setLost(true);
        return true;
    }
    return false;
}

if (!recursion) {
    gameBoard->incrementRevealed();
}

// If the number is 0 and flood fill is currently occuring, reveal the square
if (numberInSquare == 0) {

    gameBoard -> setSprite(pointX, pointY, 17, 49, 16, 16);

    if ((boardWidth * boardHeight) - gameBoard->getRevealed() == numBombs) {
        gameBoard->setButton(72, 24, 24, 24);
        cout << "win";
        gameBoard->setLost(true);
        return true;
    }
    return false;
}
...
```

**See full code at [https://github.com/AlexKernot/Minesweeper](https://github.com/AlexKernot/Minesweeper)**
<hr>

## **Contact me**

**You can contact me at the following:**
- Email - alex.kernot04@gmail.com<br />
- Instagram - [alex_kernot](https://www.instagram.com/alex_kernot/)

___
