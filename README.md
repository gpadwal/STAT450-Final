# STAT450-Final

Add R code as needed

library(ggplot2)
library(dplyr)
library(lubridate)
library(tidyverse)
phd_field <- readr::read_csv("https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2019/2019-02-19/phd_by_field.csv")
phd_field

## Check year over year trend
ggplot(phd_field,aes(year)) +geom_col(aes(x = year, y = n_phds),stat = "identity")+
xlab("Year") + ylab("Number of PhDs Issued")

## Check Which field is most popular
ggplot(phd_field) +geom_bar(aes(x = n_phds, y = broad_field),stat = "identity") +
xlab("Number of PhDs Issued") + ylab("Field")
