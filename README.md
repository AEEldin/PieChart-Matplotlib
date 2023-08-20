# Pie Chart Matplotlib
In this tutorial, we would like to create pie charts using Python's Matplotlib



### Prepare the matplotlib library.

This tutorial is using Python version 3.8, as a very stable version. With a ready python on your computer, check the following commands:

> python3 --version

> pip3 --version

> pip3 install matplotlib


Create a .py file, import the library, and you can also check the version of the matplotlib library as follows:
```
import matplotlib                # first step is to import the library
print(matplotlib.__version__)    # let's first check the version used
```

The pyplot is a submodule we will use where most of the Matplotlib utilities exist

```
import matplotlib.pyplot as plt  # let's import such submodule with an alias of plt
```



### Part 1: Creating a simple pie chart

With Pyplot, you can use the pie() function to draw pie charts. The pie() function accepts an array of values that represent the different parts (called wedges) of the pie. The size of each wedge equals the value of the part / the summation of all values

```
import matplotlib.pyplot as plt

values = [25,15,25,35]

plt.pie(values)
plt.show() 
```


### Part 2: adding a label for each part
The pie() function accepts a "label" parameter, which is an array of labels, a label per wedge

```
import matplotlib.pyplot as plt

values = [25,15,25,35]
displayLabels = ["Value 1", "Value 2", "Value 3", "Value 4"]

plt.pie(values, labels = displayLabels)
plt.show() 
```


### Part 3: change the start point of the pie chart
By default, the diagram starts from the x-axis (angle 0) and moves counterclockwise till it reaches the start point. The pie() function also accepts a "startangle" parameter, which defines the start angle of the pie chart

```
import matplotlib.pyplot as plt

values = [25,15,25,35]
displayLabels = ["Value 1", "Value 2", "Value 3", "Value 4"]

plt.pie(values, labels = displayLabels, startangle=90)
plt.show() 
```



### Part 4: Make wedge(s) stand out!
You may want to show the importance of some wedges and make them stand out compared to the other wedges. The pie() function accepts a "explode" parameter, that enables this feature. The explode parameter accepts an array, with one value per wedge representing how far from the center such wedge should be displayed

```
import matplotlib.pyplot as plt

values = [25,15,25,35]
displayLabels = ["Value 1", "Value 2", "Value 3", "Value 4"]
displayExplode = [0, 0.1, 0.2, 0]

plt.pie(values, labels = displayLabels, startangle=90, explode = displayExplode)
plt.show() 
```





### Part 5: Changing the style of the pie chart


+ Shadows can be added to the pie chart via the shadows parameter in the pie()
```
plt.pie(values, labels = displayLabels, explode = displayExplode, shadow = True)
plt.show() 
```

+ The color of each wedge is assigned randomly by default; however, you can set the color for each wedge

```
displayColors = ["black", "blue", "red", "#4CAF50"]
plt.pie(values, labels = displayLabels, explode = displayExplode, colors = displayColors)
plt.show() 
```

+ You can also include the legend on the pie chart using the legend() function

```
displayColors = ["black", "blue", "red", "#4CAF50"]
plt.pie(values, labels = displayLabels)
plt.legend(title = "The Piechart Legend")
plt.show() 
```

