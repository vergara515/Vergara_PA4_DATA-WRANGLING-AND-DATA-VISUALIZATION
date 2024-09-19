# ECE2112: Experiment 3

This respiratory contains Python codes using PANDAS, Seaborn, and Matplotlib libraries for the given programming problems. Furthermore, solutions and explanations for each problem are written in detail to further help understand each line of code and its purpose.

# ECE BOARD EXAM PROBLEM

The ECE BOARD EXAM PROBLEM has two parts. The first part uses Data wrangling to filter out the necessary data in the data frame, while the second part uses Data visualization to plot the data in a graph needed for interpretation. 

The problem starts by accessing the PANDAS Library to load the data set needed.

- _Functions used and their descriptions:_

1. **'import pandas as pd'** - This function is used to access the Pandas Library.

2. **'df_ece'** -  The variable wherein the .csv file will be stored.

# 1. Create the following data frames based on the format provided:

In problem #1, the data set is filtered with multiple conditions according to what is needed. Moreover, this problem has two sub-problems to further understand and test the use of Data wrangling. 

# a. Instrumentation and Luzon Data Frame

In this problem, several functions were used to get the following 'Name,' 'GEAS,' and 'Electronics > 70' from the students who have the Instrumentation track and from Luzon. Accordingly, the data frame will be called 'Instru'.

- _The line of code used for 'Instru':_

**Instru = df_ece[(df_ece['Track'] == 'Instrumentation')
        & (df_ece['Hometown'] == 'Luzon')
        & (df_ece['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]**

- _Functions used  for 'Instru' and their descriptions:_

1. **'Instru'** - The variable storing the filtered data frame.

2. **'df_ece['Track'] == 'Instrumentation''** - This function filters the data frame by including only the rows where the 'Track' column equals 'Instrumentation'.

3. **'df_ece['Hometown'] == 'Luzon''** - This function filters the data frame by including only the rows where the 'Hometown' column equals 'Luzon'.

4. **'df_ece['Electronics'] > 70'** - This function filters the rows to include only those whose 'Electronics' column has a value greater than 70.

5. **'[['Name', 'GEAS', 'Electronics']]'** - After the filters are applied, this function selects only the 'Name', 'GEAS', and 'Electronics' columns from the filtered data frame.

Moreover, these conditions are combined using the logical AND operator **'&'**, meaning that all conditions must be true for a row to be selected.

# b. Mindanao and Female Data Frame

In this problem, several functions where used to get the following 'Name', 'GEAS', and 'Average >= 55' from the students which are from Luzon and are Female. To get the 'Average', the values for the columns 'Math', 'Electronics', 'GEAS', and 'Communication' are averaged. Accordingly, the data frame will be called 'Mindy'.

- _The line of code used for 'Average':_

**df_ece['Average'] = df_ece[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)**

- _Functions used for 'Average' and their descriptions:_

1. **'df_ece[['Math', 'Electronics', 'GEAS', 'Communications']]'** - This function selects the columns 'Math', 'Electronics', 'GEAS', and 'Communications' from the data frame 'df_ece'.

2. **'.mean(axis=1)'** - The '.mean()' functions to calculate the average of the selected columns, while 'axis=1' ensures that each student's mean calculated is row-wise.

3. **'df_ece['Average']'** - The variable used to store each student's average in the data frame 'df_ece'.

---

- _The line of code used for 'Mindy':_

**Mindy = df_ece[(df_ece['Hometown'] == 'Mindanao')
        & (df_ece['Gender'] == 'Female')
        & (df_ece['Average'] >= 55)][['Name', 'Track', 'Electronics', 'Average']]**

- _Functions used for 'Mindy' and their descriptions:_

1. **'Mindy'** - The variable where the filtered data frame is stored.

2. **'df_ece['Hometown'] == 'Mindanao''** - This function filters the data frame by including only the rows where the 'Hometown' column equals 'Mindanao'.

3. **'df_ece['Gender'] == 'Female''** - This function filters the data frame by including only the rows where the 'Gender' column equals 'Female'.

4. **'df_ece['Average'] >= 55'** - This function adds another filter, which only students whose 'Average' is greater than or equal to 55.

5. **'[['Name', 'Track', 'Electronics', 'Average']]'** - After the filters are applied, this function selects only the 'Name', 'Track', 'Electronics', and 'Average' columns from the filtered data frame.

Moreover, these conditions are all combined by using the logical AND operator **'&'**, meaning that all conditions must be true for a row to be selected.

# 2. Create a visualization that shows how different features contributes to average grade.

In problem #2, the data set is plotted in a graph. Through the use of several functions from the libraries Seaborn and Matplotlib, the graphs can be visualized and interpreted to answer the question, "Does chosen track in college, gender, or hometown contribute to a higher average score?". 

- _Functions used to prepare data visualization and their descriptions:_

1. **'import seaborn as sns'** - This function is used to access the Seaborn Library.

2. **'import matplotlib.pylot as plt'** - This function is used to access the Matplotlib Library.

---

- _Line of functions used for Boxplot #1 and their descriptions:_

1. **'plt.figure(figsize=(10, 6))'** - The function 'plt.figure()' sets the overall size of the figure. On the other hand, 'figsize=(10,6)' sets the with width = 10 and height = 6 in inches.

2. **'sns.boxplot(x='Track', y='Average', hue='Gender', data=df_ece)'** - The function 'sns.boxplot()' creates the boxplot, which visualizes the distribution of data across different categories. The argument 'x='Track'' represents the 'Track' variable in the x-axis. The argument 'y='Average'' represents the 'Average' variable in the y-axis. The argument 'hue='Gender'' splits each track's data into two box plots for Male and Female. Lastly, 'data=df_ece' contains the data going to be used.

3. **'plt.title('Average Grade by Track and Gender')'** - This line of function sets the title of the plot, which in this case has the title 'Average Grade by Track and Gender' to make the plot more understandable.

4. **'plt.show()'** - This function renders and displays the plot.

---

- _Line of functions used for Boxplot #2 and their descriptions:_

1. **'plt.figure(figsize=(10, 6))'** - The function 'plt.figure()' sets the overall size of the figure. On the other hand, 'figsize=(10,6)' sets the with width = 10 and height = 6 in inches.

2. **'sns.boxplot(x='Hometown', y='Average', hue='Track', data=df_ece)'** - The function 'sns.boxplot()' creates the boxplot, which visualizes the distribution of data across different categories. The argument 'x='Hometown'' represents the 'Hometown' variable in the x-axis. The argument 'y='Average'' represents the 'Average' variable in the y-axis. The argument 'hue='Track'' splits each hometown's data into three box plots for Instrumentation, Communication, and Microelectronics. Lastly, 'data=df_ece' contains the data going to be used.

3. **'plt.title('Average Grade by Hometown and Track')'** - This line of function sets the title of the plot, which in this case has the title 'Average Grade by Hometown and Track' to make the plot more understandable.

4. **'plt.show()'** - This function renders and displays the plot.

---

- _Line of functions used for Boxplot #3 and their descriptions:_

1. **'plt.figure(figsize=(10, 6))'** - The function 'plt.figure()' sets the overall size of the figure. On the other hand, 'figsize=(10,6)' sets the with width = 10 and height = 6 in inches.

2. **'sns.boxplot(x='Hometown', y='Average', hue='Gender', data=df_ece)'** - The function 'sns.boxplot()' creates the boxplot, which visualizes the distribution of data across different categories. The argument 'x='Hometown'' represents the 'Hometown' variable in the x-axis. The argument 'y='Average'' represents the 'Average' variable in the y-axis. The argument 'hue='Gender'' splits each hometown's data into three box plots for Luzon, Visayas, and Mindanao. Lastly, 'data=df_ece' contains the data going to be used.

3. **'plt.title('Average Grade by Hometown and Gender')'** - This line of function sets the title of the plot, which in this case has the title 'Average Grade by Hometown and Gender' to make the plot more understandable.

4. **'plt.show()'** - This function renders and displays the plot.

# Does chosen track in college, gender, or hometown contributes to a higher average score?

From the boxplots generated, it can be inferred that the chosen track in college, gender, or hometown does contribute to a higher average score. 

Based on the boxplot of 'Average Grade by Track and Gender', it can be ruled that the male students in the Communication track seem to get higher average grades, while the Microelectronics track favors female students more. When it comes to the Instrumentation track, gender does not significantly impact the average score; however, gender does have a noticeable impact in Communications and Microelectronics.

Based on the boxplot of 'Average Grade by Hometown and Track', it suggests that students from Luzon perform better on average, especially in the Communication and Microelectronics tracks. When it comes to tracks, the Microelectronics track seems to yield higher average scores overall. It can also be observed that students with a Microelectronics track and are from Luzon generally perform better on average.

Based on the boxplot of 'Average Grade by Hometown and Gender', it can be infered that the Female and Male students from Luzon have higher average scores than Visayas and Mindanao. On the other hand, Female students from Mindanao have the lowest range of average scores, while both Females and Males in Visayas perform average, with one Female outlier.

In conclusion, by comparing all these boxplots altogether, it can be observed that the three factors- track, gender, and hometown- do contribute to the differences in average scores; however, their impact varies depending on the combination. But, it should also be noted that Hometown is the only trait that consistently contributed to the higher average score, regardless of combination. This is because Gender and Track did not matter when Hometown was involved, as students in Luzon always scored higher. Moreover, the Microelectronics track performed better on average, while gender influenced the performance on the track.
