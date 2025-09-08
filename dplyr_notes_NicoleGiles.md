---
title: "to-do 4, dplyr Notes"
author: "Nicole Giles"
date: "2025-09-08"
output: gfm
---

# Chapter 3 *dplyr*


**glimpse(dataset_name)**: shows you all columns, good summary when there’s lots of columns


First argument in dplyr verb is always a data frame
The subsequent arguments typically describe which columns to operate on using the variable names (without quotes)
The output is always a new data frame.


**pipe:**  |> , to combine multiple verbs  
**filter():** allows you to keep rows based on the values of the columns  
**arrange():** changes the order of the rows based on the value of the columns  
**arrange(desc())**: reorders the data frame based on that column in descending order  
**distinct():** finds all the unique rows in a dataset, most of the time you’ll want the distinct combination of some variables, so you can also optionally supply column names  
**.keep_all = TRUE:** put this in distinct() so that you can keep the other columns when filtering   
**count():** to find the number of occurrences  
**mutate():** adds new columns from calculations down with existing columns  
**select():** to rapidly zoom in on a useful subset using operations based on the names of the variables  
 **select(where(is.character)):** to find all columns that are characters   
Inside of select(), you can use the following:  
**starts_with("abc"):** matches names that begin with “abc”.  
**ends_with("xyz"):** matches names that end with “xyz”.  
**contains("ijk"):** matches names that contain “ijk”.  
**num_range("x", 1:3):** matches x1, x2 and x3.  
You can rename variables as you select() them by using = .   
If you want to keep all the existing variables and just want to rename a few, you can use **rename()** instead of select().  
**relocate():** to move variables around, by default moves variables to the front   
**any_of():** doesn't check for missing variables. It is useful with negative selections, when you would like to make sure a variable is removed.  
**all_of():**  for strict selection. If any of the variables in the character vector is missing, an error is thrown.  
**summary():** if being used to calculate a single summary statistic, reduces the data frame to have a single row for each group  
**n():** h returns the number of rows in each group:  


There are five handy functions that allow you to extract specific rows within each group:  
**df |> slice_head(n = 1)** takes the first row from each group.  
**df |> slice_tail(n = 1)** takes the last row in each group.  
**df |> slice_min(x, n = 1)** takes the row with the smallest value of column x.  
**df |> slice_max(x, n = 1)** takes the row with the largest value of column x.  
**df |> slice_sample(n = 1)** takes one random row.  
 

**group_by():** used to divide your dataset into groups meaningful for your analysis. The main advantage of group_by() over .by is when you want to apply multiple verbs in a row to the same grouping structure.  


**ungroup():** to remove grouping from a data frame  

