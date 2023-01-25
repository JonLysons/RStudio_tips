# RStudio Tips and Tricks

### Getting started

#### Install packages

`install.packages("tidyverse")`

`install.packages("skimr")`

`install.packages("janitor")`

#### Load the packages

`library(tidyverse)` Used to help handling data easier

`library(lubridate)` Used to make handling dates easier

`library(dplyr)` Used to make data manipulation easier

`library(readr)` Used to upload a variety of files

`library(readxl)` Used to upload Excel files

`library(skimr)` Used to provide summary statistics

`library(janitor)` Used to clean dirty data

`library(ggplot2)` Used to create graphs

### Uploading a dataset

To import a dataset and give it a new name use `Data_Filename <- read_csv("desktop/folder/spreadsheet.csv")`

Use `head(Data_Filename)` to see key info about the data file

Use `colnames(Date_Filename)` to see the column headings

Use `str(Date_Filename)` to summarise the data frame

Use `new_df <- select(Data_Filename, 'heading1', 'heading')` To create a new dataframe based on a couple of headings

Use `as_tibble(Data_Filename)` returns top 10 rows in a neat table

Use `View(Data_Filename)` to view the dataset in a new window: note the cap V.

### Combing datasets into a single dateset

To list the dataframes use `ls()`

To remove a dataframe use `rm(Data_Filename)`

To combine datasets by adding more dataframes by row, use `rbind`

`new_datframe <- rbind(data_, data_b)`

### Exporting a dateset as a .CSV

`write.csv(NameOfDataset, "NameOfFileToBeWritten.csv")`

### Adding and changing column heads

`Data_Filename$newColumn` Use the `$` to add a new column

`Data_Filename['newColumn']` Use the `[]` to add a new column

`New_Data_Filename <- cbind(Data_Filename, newColumn)` Use the `cbind` to add a new column

### Change attributes of a column

Use `mutate`

### Creating the mean of a column

```
New_Data_File <- Data_Filename %>%
  group_by(colunm_name) %>%
  summarise(mean_header = round(mean(colunm_name2), 2))
  ```
### Create a smaller dataframe using group_by
```
New_Data_File <- Bata_Filename %>%
  group_by(colunm_name) %>%
  count(new_col, name = "number")
  ```
### Create a bar chart
```
ggplot(data = New_Data_File) + 
  (aes(x = colunm_name, y= number, fill = colunm_name2, width = 0.75)) +
  geom_col(position = "dodge") +
  labs(title = "Headline Here", x = "X Axis legend", y = "Y Axis legend") +
  scale_fill_brewer(palette = "Set1") +
  scale_y_continuous(breaks = c(0, 50000, 100000, 150000, 200000, 250000, 300000, 350000, 400000, 450000, 500000)) +
  theme(axis.text.x = element_text(angle = 60, hjust =1))
  ```


