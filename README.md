# Week-4-dplyr-activity-
Week 4 activity R language 
#Week 4: dplyr package

#Task: Write the function to get a dataset from Base R: Titanic
#and give the dataframe a new name of your choice
#(hint: you will want your data to be a dataframe. Use the function: as.data.frame(Titanic))
New_Titanic <- as.data.frame(Titanic)
print(New_Titanic)

#See the top rows of the data
#TASK: Write the function to see the top rows of the data
head(New_Titanic)

#Install and call the package dplyr
#TASK: Write the functions to install and call dplyr
# Install the dplyr package (if not already installed)
install.packages("dplyr")

#Let's just see the Survived and Sex columns
#Task: Write the function to 'select' the Survived and Sex columns 
#(hint: use the 'select' function)
select(New_Titanic, Survived, Sex)

#Let's name the dataset with just the two columns, Survived and Sex
#TASK: Write the function to save the two columns as one new dataset
#and give it a name
selected_column <- select(New_Titanic, Survived, Sex)
print(selected_column)


#Let's get rid of the Sex column in the new dataset created above
#TASK: Write the function that deselects the sex column
#(hint: use the 'select' function to not select a -column)
selected_column <- select(New_Titanic, Survived)
print(selected_column)

#Let's rename a column name
#TASK: Write the function that renames 'Sex' to 'Gender'
rename(New_Titanic, Gender = Sex)

#Let's make a new dataframe with the new column name
#TASK: Write the function that names a new dataset that includes the 'gender' column
New_dataframe <- select(New_Titanic, Survived, Gender = Sex)
print(New_dataframe)

#Let's 'filter' just the males from our dataset
#TASK: Write the function that includes only rows that are 'male'
Male_data <- filter(New_dataframe, Gender == "Male")
print(Male_data)

#Let's 'arrange' our data by gender (not the data you just filtered)
#TASK: Write the function to group the data by gender (hint: arrange())
arranged_data <- arrange(New_dataframe, Gender)
print(arranged_data)

#Let's see how many people were examined in the dataset (total the frequency in the original dataframe)
#TASK: Sum the Freq column
#TASK: After you run it, write the total here: 2201
sum(New_Titanic$Freq)

#Since we have a males dataset, let's make a females dataset
#TASK: Write the function that includes only rows that are 'female'
Female_data <- filter(New_dataframe, Gender == "Female")
print(Female_data)

#And now let's join the males and females
#TASK: Write the function that joins the male and female rows 
#(hint: try using 'union' or 'bind_rows')
Male_Female_data <- union(Male_data, Female_data)
head(Male_Female_data)


#Optional Task: add any of the other functions 
#you learned about from the dplyr package
