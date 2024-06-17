# ANA515Assign2

# First, install and load the necessary package if you haven't already
# install.packages("readr")
library(readr)

# Read the CSV file from the URL and assign it to a dataframe object
drug_use <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/drug-use-by-age/drug-use-by-age.csv")

# Display the first few rows of the dataframe to verify the data was loaded correctly
head(drug_use)

# Load necessary packages
library(readr)
library(dplyr)

# Read the CSV file from the URL and assign it to a dataframe object
drug_use <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/drug-use-by-age/drug-use-by-age.csv")

# Rename columns for clarity
colnames(drug_use) <- c("age_group", "alcohol_use", "alcohol_frequency",
"marijuana_use","marijuana_frequency", "cocaine_use",
"cocaine_frequency", "crack_use",
"crack_frequency", "heroin_use", "heroin_frequency",
"hallucinogen_use", "hallucinogen_frequency", "inhalant_use",
"inhalant_frequency", "pain_reliever_use", "pain_reliever_frequency",
"oxycontin_use", "oxycontin_frequency", "tranquilizer_use",
"tranquilizer_frequency", "stimulant_use", "stimulant_frequency",
"meth_use", "meth_frequency", "sedative_use", "sedative_frequency")

# Convert any dates into a "Date" format (if applicable)
# There are no dates in this dataset, so this step is not needed

# Subset the dataset to keep at least four columns
cleaned_drug_use <- select(drug_use, age_group, alcohol_use, marijuana_use, cocaine_use)

# Display the first few rows of the cleaned dataframe
head(cleaned_drug_use)

# Load necessary packages
library(readr)

# Read the CSV file from the URL and assign it to a dataframe object
drug_use <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/drug-use-by-age/drug-use-by-age.csv")

# Select three columns of interest
selected_columns <- drug_use %>%
select("alcohol_use", "marijuana_use", "cocaine_use")

# Check the number of missing values
missing_values <- colSums(is.na(selected_columns))

# Check the number of missing values (According to checking process, there is no missing values)
missing_values

# Summary of selected columns

summary_stats <- selected_columns %>%
summarize(
min_alcohol_use = min(alcohol_use, na.rm = TRUE), 
max_alcohol_use = max(alcohol_use, na.rm = TRUE), 
mean_alcohol_use = mean(alcohol_use, na.rm = TRUE), 
min_marijuana_use = min(marijuana_use, na.rm = TRUE), 
max_marijuana_use = max(marijuana_use, na.rm = TRUE), 
mean_marijuana_use = mean(marijuana_use, na.rm = TRUE), 
min_cocaine_use = min(cocaine_use, na.rm = TRUE), 
max_cocaine_use = max(cocaine_use, na.rm = TRUE), 
mean_cocaine_use = mean(cocaine_use, na.rm = TRUE)
)

# Display the summary
summary_stats



