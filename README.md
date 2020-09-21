#### Week2_Quiz_Courera_JH

#### install.packages("jsonlite")
library(jsonlite)

#### install.packages("httr")
library(httr)

auth <- authenticate("your user name", "your password", type = "basic")

#### Get OAuth credentials
req <- GET("https://api.github.com/users/jtleek/repos", config = auth)

#### Extract content from a request
json1 = content(req)

#### Convert to a data.frame
gitDF = jsonlite::fromJSON(jsonlite::toJSON(json1))

#### Subset data.frame
gitDF[gitDF$full_name == "jtleek/datasharing", "created_at"] 
