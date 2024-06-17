```{r}
library(readr)
library(dplyr)
```

```{r}
drug_use <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/drug-use-by-age/drug-use-by-age.csv")
```
```{r}
head(drug_use)
```
```{r}
colnames(drug_use) <- c("age_group", "alcohol_use", "alcohol_frequency",
                        "marijuana_use", "marijuana_frequency", "cocaine_use",
                        "cocaine_frequency", "crack_use", "crack_frequency",
                        "heroin_use", "heroin_frequency", "hallucinogen_use",
                        "hallucinogen_frequency", "inhalant_use",
                        "inhalant_frequency", "pain_reliever_use",
                        "pain_reliever_frequency", "oxycontin_use",
                        "oxycontin_frequency", "tranquilizer_use",
                        "tranquilizer_frequency", "stimulant_use",
                        "stimulant_frequency", "meth_use", "meth_frequency",
                        "sedative_use", "sedative_frequency")
```

```{r}
cleaned_drug_use <- select(drug_use, age_group, alcohol_use, marijuana_use,
                           cocaine_use)
```

```{r}
head(cleaned_drug_use)
```
```{r}
selected_columns <- drug_use %>%
  select("alcohol_use", "marijuana_use", "cocaine_use")
```

```{r}
missing_values <- colSums(is.na(selected_columns))
```

```{r}
missing_values
```

```{r}
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
```

```{r}
summary_stats
```
