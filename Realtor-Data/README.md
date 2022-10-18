# Export R to Excel

Code and Excel sheet included in folder. 

How: install.packages("writexl")

library("writexl")

#write_xlsx(the dataframe name,"path to store the Excel file\\file name.xlsx")

#example:

write_xlsx(dataframe,"~/Desktop/realtor-data.xlsx")

