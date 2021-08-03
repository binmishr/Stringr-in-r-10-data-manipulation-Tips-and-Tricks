# Stringr-in-r-10-data-manipulation-Tips-and-Tricks

Stringr in r data manipulation Tips and Tricks, In this tutorial we are going to discuss useful functions and expressions in stringr package.
Stringr in r

Variety of functions available in stringr package but we are going cover only important functions in our day-to-day data analysis.

library(stringr)

1. Word Length

statement<-c("R", "is powerful", "tool", "for data", "analysis")

Suppose if you want to find the length of each word, you can use str_length

statement
"R"           "is powerful" "tool"        "for data"    "analysis"
str_length(statement)
1 11  4  8  8

2. Concatnate

If you want to join the string str_c will be useful.



str_c(statement,collapse=" ")

“R is powerful tool for data analysis”

str_c("test",1:10, sep="-")[1] "test-1"  "test-2"  "test-3"  "test-4"  "test-5"  "test-6"  "test-7"  "test-8"  "test-9"
[10] "test-10"
str_c("test",1:10, sep=",")
[1] "test,1"  "test,2"  "test,3"  "test,4"  "test,5"  "test,6"  "test,7"  "test,8"  "test,9"
[10] "test,10"

3. NA Replace

Now will see how to handle missing data’s

str_c(c("My Name", NA, "Jhon"),".")
"My Name." NA         "Jhon."

So you can see missing value is not concatenated. This we can overcome based on str_replace_na()

replace NA with . or character

str_replace_na(c("My Name", NA, "Jhon"),".")
"My Name" "."       "Jhon"

4. String Extraction

If you want to extract the substring then str_sub will be handy.

str_sub(statement,1,5)
"R"     "is po" "tool"  "for d" "analy"

Now you can see the first 5 characters extracted from the string vector.



If you know the length of the string you can update your string also.

str_sub(statement, 4,-1)<-"Wow"
statement
"RWow"   "is Wow" "tooWow" "forWow" "anaWow"

5. Split

If you want to split the string based on pattern, str_split will be useful.

str_split(statement,pattern=" ")
[[1]]
[1] "RWow"
[[2]]
[1] "is"  "Wow"
[[3]]
[1] "tooWow"
[[4]]
[1] "forWow"
[[5]]
[1] "anaWow"

6. Subset

Suppose if you want to subset word in the particular pattern you can make use of str_subset

Handling missing values in R Programming »

str_subset(colors(),pattern="green")
[1] "darkgreen"         "darkolivegreen"    "darkolivegreen1"   "darkolivegreen2" 
 [5] "darkolivegreen3"   "darkolivegreen4"   "darkseagreen"      "darkseagreen1"   
 [9] "darkseagreen2"     "darkseagreen3"     "darkseagreen4"     "forestgreen"     
[13] "green"             "green1"            "green2"            "green3"          
[17] "green4"            "greenyellow"       "lawngreen"         "lightgreen"      
[21] "lightseagreen"     "limegreen"         "mediumseagreen"    "mediumspringgreen"
[25] "palegreen"         "palegreen1"        "palegreen2"        "palegreen3"      
[29] "palegreen4"        "seagreen"          "seagreen1"         "seagreen2"       
[33] "seagreen3"         "seagreen4"         "springgreen"       "springgreen1"    
[37] "springgreen2"      "springgreen3"      "springgreen4"      "yellowgreen"
If  you want to extract colors start with orange or end with red then ^$ will be helpful
str_subset(colors(),pattern="^orange|red$")
1] "darkred"         "indianred"       "mediumvioletred" "orange"          "orange1"      
 [6] "orange2"         "orange3"         "orange4"         "orangered"       "orangered1"    
[11] "orangered2"      "orangered3"      "orangered4"      "palevioletred"   "red"           
[16] "violetred"

^ indicate the starting of the string and $ indicate string ending with

If you want to extract characters or numbers from string str_extract will be useful

list<-c("Hai1", "my 10", "Name 20")
str_extract(list,pattern="[a-z]")

“a” “m” “a”

If you want full word then you can use

str_extract(list,pattern="[a-z]+")

“ai”  “my”  “ame”
7. html view

If you want to see the html vie output then you can use str_view



str_view(statement,"a.")

Return first match in first string
9. Count

str_count for counting the character

str_count(statement,"[ae]")
0 0 0 0 2

9. Location

str_locate(statement,"[ae]")
start end
[1,]    NA  NA
[2,]    NA  NA
[3,]    NA  NA
[4,]    NA  NA
[5,]     1   1

str_locate will display the first match


10. Lower/Upper case

For lower case letters

str_to_lower(statement)

“rwow”   “is wow” “toowow” “forwow” “anawow”

str_to_upper(statement)

“RWOW”   “IS WOW” “TOOWOW” “FORWOW” “ANAWOW”

For case, the sensitive first letter in upper case and rest will be lower case

apply family in r apply(), lapply(), sapply(), mapply() and tapply()

str_to_title(statement)

“Rwow”   “Is Wow” “Toowow” “Forwow” “Anawow”

?stringr and go to index you will get all stringr functions.
