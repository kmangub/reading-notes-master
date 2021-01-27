# Matplotlib

Matplotlib is a package commonly used for Python for its 2D-graphics visualization. 

`Ipython` is an interactive shell that contain features such as inputs and outputs, shell commands, debugging and more. In the command line, we start off with `-pylab ` to access the interactive matplotlib sessions.

`pyplot` is a plotting library closely modeled from MatLab(TM)

### Simple Plot

To make a plot for sin and cosine, we input the following:
```
import numpy as np

X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)
```

To run it:

```
$ python exercice_1.py
```
## Modifying Graphs

The graphs that are shown can be modified to our liking, such as changing color and line width. An example of the code is shown below:

```
plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```
## Setting Limits

Another way to change the graph is by setting the limits of the x and y axis:

```
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```
## Changing Tick Marks

We can change the tick marks to reflect radian values:
```
plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
plt.yticks([-1, 0, +1])
```

## Modifying Boundaries

Spines are the lines connecting the axis tick marks and noting the boundaries of the data area. Since we are dealing with sine and cosine graphs, it's best to remove the top and right boundaries and move the bottom and left to origin 0. To do that, we input this:

```
ax = plt.gca()
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
ax.xaxis.set_ticks_position('bottom')
ax.spines['bottom'].set_position(('data',0))
ax.yaxis.set_ticks_position('left')
ax.spines['left'].set_position(('data',0))
```

## Setting Legends

Legends are a great way to show what the graph represents. To input legends:

```
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-", label="cosine")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-", label="sine")

plt.legend(loc='upper left', frameon=False)
```
## Annotating Points

We can annotate a specific point to highlight its result:

```
t = 2*np.pi/3
plt.plot([t,t],[0,np.cos(t)], color ='blue', linewidth=1.5, linestyle="--")
plt.scatter([t,],[np.cos(t),], 50, color ='blue')

plt.annotate(r'$\sin(\frac{2\pi}{3})=\frac{\sqrt{3}}{2}$',
             xy=(t, np.sin(t)), xycoords='data',
             xytext=(+10, +30), textcoords='offset points', fontsize=16,
             arrowprops=dict(arrowstyle="->", connectionstyle="arc3,rad=.2"))

plt.plot([t,t],[0,np.sin(t)], color ='red', linewidth=1.5, linestyle="--")
plt.scatter([t,],[np.sin(t),], 50, color ='red')

plt.annotate(r'$\cos(\frac{2\pi}{3})=-\frac{1}{2}$',
             xy=(t, np.cos(t)), xycoords='data',
             xytext=(-90, -50), textcoords='offset points', fontsize=16,
             arrowprops=dict(arrowstyle="->", connectionstyle="arc3,rad=.2"))
```

## Semi-Transparent Tick Backgrounds

Since the lines are bold colors, it's hard to see what the tick marks are. An easy fix would be to set the tick's background to semi-transparent. So:

```
for label in ax.get_xticklabels() + ax.get_yticklabels():
    label.set_fontsize(16)
    label.set_bbox(dict(facecolor='white', edgecolor='None', alpha=0.65 ))
```

## Figures, Subplots, and Axes Ticks 

Matplotlib gives us control on what we name the graph. Axes allows us to plot subplots. Tick locators have a variety of locators such as fixed numbers, log, auto, and linear. 

## Animation 

The most easy way to make an animation in matplotlib is to declare a FuncAnimation object that specifies to matplotlib what is the figure to update, what is the update function and what is the delay between frames.

We can make cool animations, such as droplet effect, and implement it on top of a map. One case would be to plot the drops where earthquakes occur. 

## Other Types of Plots

- Scatter
- Bar
- Contour
- IMSHOW
- Quiver Plot
- Pie Chart
- Grid
- Multiplot
- Polar Axis
- 3D Plots
- Text plots