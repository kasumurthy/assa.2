# Assignment_1.2
1.2
1.What should be the output of the following Script?.
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v%/%t)
OUTPUT  :  0 1 1
 

2. You have 25 excel files with names as xx_1.xlsx, xx_2.xlsx,........xx_25.xlsx in a dir.
Write a program to extract the contents of each excel sheet and make it one df.

 setwd("D:/DA/R")  
# read the files in directory
file.list <- list.files(pattern='*.xlsx')      

# data frame by column with column id
df.list <- lapply(file.list, read_excel)
df1 <- rbindlist(df.list, idcol = "id",fill = TRUE)
View(df1)
 
 


3. If the above 25 files were csv files, what would be your script to read?
 
 setwd("D:/DA/R")

file.list <- list.files(pattern='*.csv') # read the files in directory


# data frame by column with column id
df.list <- lapply(file.list, read.csv)
df_csv <- rbindlist(df.list, idcol = "id",fill = TRUE)
View(df_csv)
