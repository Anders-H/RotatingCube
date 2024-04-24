# Rotating Cube

A direct port of the rotating cube by Tony Schiffbauer from Commodore 128 to JavaScript. The original code:

```
10 rem rotating cube
15 rem 2024 the real tonyrocks!
20 graphic 1,1
30 dim rx:dim l:dim fs:dim c:dim s
40 dim x(8):
50 dim y(8):
60 dim z(8):
70 dim xt:dim yt
80 dim np
90 dim vx(8):dim vy(8):
100 rx = -0.1 : rem rotation angle x
110 l = 80 : fs = 200 : l = l /2
120 rem label_35
130 scnclr
140 x(1) = -l : y(1) = -l : z(1) = -l
150 x(2) = -l: y(2) = l: z(2) = -l
160 x(3) = l: y(3) = l: z(3) = -l
170 x(4) = l : y(4) = -l : z(4) = -l
180 x(5) = -l : y(5) = -l: z(5) = l
190 x(6) = -l : y(6) = l: z(6) = l
200 x(7) = l: y(7) = l: z(7) = l
210 x(8 ) = l: y(8 ) = -l: z(8 ) = l
220 rx = rx + 0.1 : c = cos(rx): s = sin(rx)
300 for np = 1 to 8
310 rem rotation on x axis
320 yt = y(np): y(np) = c*yt-s*z(np): z(np) = s*yt + c*z(np)
330 rem rotation on y axis
340 xt = x(np): x(np) = c*xt+s*z(np): z(np)=-s*xt+c*z(np)
350 rem rotation on z axis
360 xt = x(np) :x(np)=c*xt-s*y(np) : y(np) = s*xt+c*y(np)
370 rem points projections and translations to screen coordinates
380 vx(np) = 160 + (x(np)*fs)/(z(np)+fs)
390 vy(np) = 100 + (y(np)*fs)/(z(np)+fs)
400 next
430 scnclr
500 draw 1, vx(1), vy(1) to vx(2),vy(2) to vx(3), vy(3) to vx(4),vy(4) to vx(1), vy(1)
520 draw 1, vx(5), vy(5) to vx(6 ),vy(6) to vx(7), vy(7) to vx(8 ),vy(8 ) to vx(5), vy(5)
540 draw 1, vx(8 ), vy(8 ) to vx(5),vy(5): draw 1, vx(1), vy(1) to vx(5), vy(5)
550 draw 1, vx(4), vy(4) to vx(8 ),vy(8 ) : draw 1, vx(2), vy(2) to vx(6), vy(6)
560 draw 1, vx(3), vy(3) to vx(7),vy(7)
700 goto 120
```

The ported code [is here.](https://github.com/Anders-H/RotatingCube/blob/main/cube.html)

And the result [can be viewed here.](https://winsoft.se/temp/cube.html))
