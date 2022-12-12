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

### Uploading a dataset

To import a dataset and give it a new name use `Date_Filename <- read_csv("desktop/folder/spreadsheet.csv")`

Use `head(Date_Filename)` to see key info about the data file

Use `colnames(Date_Filename)` to see the column headings

Use `str(Date_Filename)` to summarise the data frame

Use `new_df <- select(Date_Filename, 'heading1', 'heading')` To create a new dataframe based on a couple of headings

### Combing datasets into a single dateset

To list the dataframes use `ls()`

To remove a dataframe use `rm(Data_Filename)`

To combine datasets by adding more dataframes by row, use `rbind`

`new_datframe <- rbind(data_, data_b)`







