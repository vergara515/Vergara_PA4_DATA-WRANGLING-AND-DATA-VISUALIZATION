# ECE2112: Experiment 3

This respiratory contains Python codes using PANDAS, Seaborn, and Matplotlib libraries for the given programming problems. Furthermore, solutions and explanations for each problem are written in detailed to further help understand each line of code and their purpose.

# ECE BOARD EXAM PROBLEM

The ECE BOARD EXAM PROBLEM has two parts wherein the first part uses Data wrangling to filter out the necessary data needed in the data frame, while the second part uses Data visualition to plot the data in a graph, needed for interpretation. 

The problem starts by accessing the PANDAS library to load the data set needed.

- _Functions used and their descriptions:_

1. **'import pandas as pd'** - This function is used to access the Pandas library.

2. **'df_ece'** -  The variable wherein the .csv file will be stored.

# 1. Create the following data frames based on the format provided:

In problem #1, the data set are filtered with multiple conditions according to what is needed. Moreover, there are two sub-problems in this problem to further understand and test the use of Data wrangling. 

# a. Instrumentation and Luzon Data Frame

In this problem, several functions where used to get the following 'Name', 'GEAS', and 'Electronics > 70' from the students which has the Instrumentation track and from Luzon. Accordingly, the data frame will be called 'Instru'.

- _The line of code used for 'Instru':_

**Instru = df_ece[(df_ece['Track'] == 'Instrumentation')
        & (df_ece['Hometown'] == 'Luzon')
        & (df_ece['Electronics'] > 70)][['Name', 'GEAS', 'Electronics']]**

- _Functions used  for 'Instru' and their descriptions:_

1. **'Instru'** - The variable where the filtered data frame is stored.

2. **'df_ece['Track'] == 'Instrumentation''** - This function filters the data frame by including only the rows where the 'Track' column equals 'Instrumentation'.

3. **'df_ece['Hometown'] == 'Luzon''** - This function filters the data frame by including only the rows where the 'Hometown' column equals 'Luzon'.

4. **'df_ece['Electronics'] > 70'** - This function filters the rows to include only those which 'Electronics' column has a value greater than 70.

5. **'[['Name', 'GEAS', 'Electronics']]'** - After the filters are applied, this function selects only the 'Name', 'GEAS', and 'Electronics' columns from the filtered data frame.

Moreover, these conditions are all combined by using the logical AND operator **'&'**, meaning that all conditions must be true for a row to be selected.

# b. Mindanao and Female Data Frame

In this problem, several functions where used to get the following 'Name', 'GEAS', and 'Average >= 55' from the students which are from Luzon and are Female. To get the 'Average', the values for the columns 'Math', 'Electronics', 'GEAS', and 'Communication' are averaged. Accordingly, the data frame will be called 'Mindy'.

- _The line of code used for 'Average':_

**df_ece['Average'] = df_ece[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)**

- _Functions used for 'Average' and their descriptions:_

1. **'df_ece[['Math', 'Electronics', 'GEAS', 'Communications']]'** - This function selects the columns 'Math', 'Electronics', 'GEAS', and 'Communications' from the data frame 'df_ece'.

2. **'.mean(axis=1)'** - The '.mean()' functions to calculate the average of the selected columns, while 'axis=1' ensures that the mean calculated is row-wise for each student.

3. **'df_ece['Average']'** - The variable used to store the average of each student in the data frame 'df_ece'.

- _The line of code used for 'Mindy':_

1. **'Mindy'** - The variable where the filtered data frame is stored.

2. **'df_ece['Hometown'] == 'Mindanao''** - This function filters the data frame by including only the rows where the 'Hometown' column equals 'Mindanao'.

3. **'df_ece['Gender'] == 'Female''** - This function filters the data frame by including only the rows where the 'Gender' column equals 'Female'.

4. **'df_ece['Average'] >= 55'** - This function adds another filter which only students whose 'Average' is greater than or equal to 55.

5. **'[['Name', 'Track', 'Electronics', 'Average']]'** - After the filters are applied, this function selects only the 'Name', 'Track', 'Electronics', and 'Average' columns from the filtered data frame.

Moreover, these conditions are all combined by using the logical AND operator **'&'**, meaning that all conditions must be true for a row to be selected.

# 2. Create a visualization that shows how different features contributes to average grade.

In problem #2, the data set are plotted in a graph. Through the us of several functions from the libraries Seaborn and Matplotlib, the graphs can be visualized and interpreted to answer the question "Does chosen track in college, gender, or hometown contributes to a higher average score?". 

- _Functions used for to prepare data visualization and their descriptions:_

1. **'import seaborn as sns'** - This function is used to access the Seaborn library.

2. **'import matplotlib.pylot as plt'** - This function is used to access the Matplotlib library.

- _Functions used for Boxplot #1 and their descriptions:_

1. **'plt.figure(figsize=(10, 6))'** - This function sets the overall size of the figure with width = 10 and height = 6 in inches.

2. **'sns.boxplot(x='Track', y='Average', hue='Gender', data=df_ece)'** - 

3. **'plt.title('Average Grade by Track and Gender')'** -

4. **'plt.show()'** - 
