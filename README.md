**Data Cleaning- Absenteeism Data analysis**
## Objective = We want to predict absenteeism from work
## Dataset 
When we look at our dataset, we see a variable that is named "Absenteeism Time in hours", which tells us how many hours an employee was absent for each specific date. This is our dependent variable. 
How can we predict this value for future observations? The other columns could be independent variables. In our regression equation, we could include some of these columns to help us understand and predict if an individual with certain characteristics is more likely to be absent from work for a certain duration, or not. 
Here are the different tasks that are needed to be executed on the data set “Absenteeism-data.csv”: 
1.	Drop the ‘ID’ column.
a.	 Employee ID is an individual identification of each person. It indicates precisely who has been away during working hours. However, this information will not improve our analysis in any way since it is just a number that is there to distinguish the individuals from one another, not to carry any numeric information. It's a nominal data which can't help explaining the absenteeism. We should thus drop this variable.
2.	Split the reasons for absence column into multiple dummy variables & Drop the “Reeason for Absence” column afterwards 
a.	IMPORTANT: We are sure that an individual has been absent from work for one and one reason only.
b.	The values 1, 2 etc. in this column are the 28 reasons for absence, that have been substituted to numbers (list of the reason available). But how should we treat this information? The values represent categories that are equally meaningful. We could have had names to describe them (disease, dentist etc.) but using numbers is the default way to work with categorical nominal variable (using a legend), and it also uses less data storage.
c.	To perform quantitative analysis, we need to add numeric meaning to our categorical nominal values by putting them in a dummy variable: an explanatory binary variable that equals 1 if a certain categorical effect is present, or 0 if the same effect is absent. We can thus group them (Classification) in the following way:
  1. Group 1: Columns 1 to 14: Diseases
  2. Group 2: Columns 15, 16, and 17: Pregnancy and giving birth.
  3. Group 3: Columns 18, 19, 20, and 21: Poisoning 
  4. Group 4: Columns 22 to 28: “Light” reasons, consultations etc.
3.	Extract the month value and the day of the week from the ‘Date’ column. Then, drop the ‘Date’ column as well: 
a.	First, you’ll need to change the data type of the date column, that is now stored as a string, to a timestamp (data type used for values representing dates and time)
4.	The columns Transportation expense (monthly, in $), Distance to Work, Age Daly Workload Average (minutes worked per day) and Body Mass Index are numerical and clean.
5.	Turn the data from the ‘Education’ column into binary data, by mapping the value of 0 to the value of 1, and the value of 1 to the rest of the values found in this column.: 
a.	Education: the numbers do not have numerical meaning, it’s simply categorical data containing integers.
b.	Values : 1 (high school), 2( graduate), 3 (post graduate), 4 (master or doctor)
