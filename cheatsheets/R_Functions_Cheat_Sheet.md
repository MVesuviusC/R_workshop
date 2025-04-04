# Commonly Used R Functions Cheat Sheet

This guide provides a quick summary of common R functions including what they do, how to use them, and their frequently used arguments.

---

## Data I/O Functions

### read.delim()
**Description:**
Reads a delimited text file into a data frame (typically tab-delimited).

**Usage:**
```r
read.delim("file_path", header = TRUE)
```

**Frequently Used Arguments:**
- `file`: The path to the file.
- `header`: Logical; indicates if the file contains a header row.
- `sep`: Field separator (default: "\t" for tab-delimited files).

---

### write.table()
**Description:**
Writes a data frame or matrix to a file.

**Usage:**
```r
write.table(data, file = "output.txt", sep = "\t", row.names = FALSE)
```

**Frequently Used Arguments:**
- `data`: The data frame or matrix to write.
- `file`: Destination file path.
- `sep`: Field separator.
- `row.names`: Logical; whether to include row names.

---

### write_tsv()
**Description:**
Writes a data frame to a tab-separated value file.

**Usage:**
```r
write_tsv(data, file = "output.tsv")
```

**Frequently Used Arguments:**
- `data`: Data frame to write.
- `file`: Destination file path.

---

## Data Manipulation Functions

### head()
**Description:**
Returns the first elements of a vector, list, or data frame.

**Usage:**
```r
head(x, n = 6)
```

**Frequently Used Arguments:**
- `x`: Object to extract from.
- `n`: Number of elements/rows to return.

---

### cbind() and rbind()
**Description:**
`cbind()` combines objects by columns; `rbind()` combines them by rows.

**Usage:**
```r
# Column bind
cbind(object1, object2)

# Row bind
rbind(object1, object2)
```

**Frequently Used Arguments:**
- Objects with compatible dimensions.

---

### merge()
**Description:**
Joins two data frames by common columns or row names.

**Usage:**
```r
merge(x, y, by = "common_column")
```

**Frequently Used Arguments:**
- `x, y`: Data frames to merge.
- `by`: Common column(s) for merging.
- `all`: Logical to perform outer join.

---

### mutate()
**Description:**
Adds new columns or transforms existing columns in a data frame.

**Usage:**
```r
mutate(data, new_var = expression)
```

**Frequently Used Arguments:**
- `data`: Input data frame.
- `new_var`: Name of new/transformed column.

---

### group_by() and summarize()
**Description:**
`group_by()` splits data into groups; `summarize()` computes summary statistics per group.

**Usage:**
```r
data %>%
  group_by(group_var) %>%
  summarize(stat = summary_function(target_var))
```

**Frequently Used Arguments:**
- `group_by`: Variables to group by.
- `summarize`: Summary functions (e.g., mean, sum).

---

### pivot_longer() and pivot_wider()
**Description:**
Reshape data from wide-to-long and long-to-wide formats (tidyverse).

**Usage:**
```r
# Wide to long
pivot_longer(data, cols = columns, names_to = "name", values_to = "value")

# Long to wide
pivot_wider(data, names_from = "name", values_from = "value")
```

**Frequently Used Arguments:**
- `data`: Input data frame.
- `cols`: Columns to pivot.
- `names_to`/`values_to`: Names for reshaped columns.

---

## Statistical & Summarizing Functions

### print()
**Description:**
Displays the value of an object to the console.

**Usage:**
```r
print(object)
```

**Frequently Used Arguments:**
- `object`: The object to be printed.
- `quote`: Logical; if TRUE, prints strings with quotes.

---

### summary()
**Description:**
Provides summary statistics (min, max, median, etc.) of an object.

**Usage:**
```r
summary(object)
```

**Frequently Used Arguments:**
- `object`: Typically a data frame or vector.

---

### mean()
**Description:**
Calculates the average of numeric data.

**Usage:**
```r
mean(x)
```

**Frequently Used Arguments:**
- `x`: Numeric vector.
- `na.rm`: Logical; ignore NA values if TRUE.

---

### median()
**Description:**
Finds the middle value of numeric data.

**Usage:**
```r
median(x)
```

**Frequently Used Arguments:**
- `x`: Numeric vector.
- `na.rm`: Logical; removes NA values.

---

### min() and max()
**Description:**
`min()` returns the smallest value; `max()` returns the largest.

**Usage:**
```r
min(x)
max(x)
```

**Frequently Used Arguments:**
- `x`: Numeric vector.
- `na.rm`: Logical; for removing NA values.

---

### t.test()
**Description:**
Performs a t-test for comparing means between two groups.

**Usage:**
```r
t.test(x, y)
```

**Frequently Used Arguments:**
- `x, y`: Numeric vectors.
- `alternative`: Hypothesis direction.
- `var.equal`: Logical; assume equal variances if TRUE.

---

### aov()
**Description:**
Performs analysis of variance (ANOVA) to test group differences.

**Usage:**
```r
aov(response ~ predictor, data = dataset)
```

**Frequently Used Arguments:**
- `formula`: Model specification.
- `data`: Data frame containing the variables.

---

### t()
**Description:**
Transposes a matrix or data frame.

**Usage:**
```r
t(x)
```

**Frequently Used Arguments:**
- `x`: Matrix or data frame.

---

## Base Plotting Functions

### plot()
**Description:**
Generates basic plots (scatter, lines, etc.) based on input.

**Usage:**
```r
plot(x, y)
```

**Frequently Used Arguments:**
- `x`: Data or formula.
- `y`: Data (if not using formula).
- `type`: Plot type (e.g., "p" for points, "l" for lines).

---

### boxplot()
**Description:**
Creates a box-and-whisker plot to display data distribution.

**Usage:**
```r
boxplot(x ~ group)
```

**Frequently Used Arguments:**
- `x`: A numeric vector or formula.
- `data`: Data frame (when using a formula).
- `col`: Box color.

---

### hist()
**Description:**
Plots a histogram to display the distribution of numeric data.

**Usage:**
```r
hist(x, n = 100)
```

**Frequently Used Arguments:**
- `x`: Numeric vector.
- `n`: Number of bins.

---

## ggplot2 Plotting Functions

### ggplot()
**Description:**
Starts a ggplot object as the base for building layered plots.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2))
```

**Frequently Used Arguments:**
- `data`: Data frame.
- `aes()`: Aesthetic mappings.

---

### geom_point()
**Description:**
Adds a scatterplot layer to a ggplot.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  geom_point()
```

**Frequently Used Arguments:**
- `color`, `size`, `alpha`: Aesthetic parameters.

---

### geom_histogram()
**Description:**
Adds a histogram layer in ggplot.

**Usage:**
```r
ggplot(data, aes(x = var)) +
  geom_histogram(bins = 30)
```

**Frequently Used Arguments:**
- `bins`: Number of bins.
- `fill`/`color`: Aesthetic properties.

---

### geom_density()
**Description:**
Adds a density estimation layer for smoothed distribution curves.

**Usage:**
```r
ggplot(data, aes(x = var, fill = group)) +
  geom_density(alpha = 0.5)
```

**Frequently Used Arguments:**
- `alpha`: Transparency.
- `adjust`: Bandwidth adjustment.

---

### geom_col()
**Description:**
Creates a bar plot layer with bar heights representing data values.

**Usage:**
```r
ggplot(data, aes(x = category, y = value)) +
  geom_col()
```

**Frequently Used Arguments:**
- `fill`, `color`: Visual appearance.

---

### geom_errorbar()
**Description:**
Adds error bars to a ggplot.

**Usage:**
```r
ggplot(data, aes(x = category, y = mean, ymin = lower, ymax = upper)) +
  geom_errorbar(width = 0.2)
```

**Frequently Used Arguments:**
- `ymin`, `ymax`: Define error range.
- `width`: Error bar width.

---

### geom_jitter()
**Description:**
Displays points with randomized noise to prevent overplotting.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  geom_jitter(width = 0.2)
```

**Frequently Used Arguments:**
- `width`, `height`: Jitter amounts.

---

### geom_smooth()
**Description:**
Adds a smooth trend line (e.g., regression) to a plot.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  geom_smooth(method = "loess", se = TRUE)
```

**Frequently Used Arguments:**
- `method`: Smoothing method.
- `se`: Logical; display confidence interval.

---

### labs()
**Description:**
Adds titles, axis labels, and captions to a ggplot.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  labs(title = "Title", x = "X Axis", y = "Y Axis")
```

**Frequently Used Arguments:**
- `title`, `x`, `y`, `caption`: Label text.

---

### facet_wrap()
**Description:**
Splits a ggplot into multiple panels based on a factor.

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  facet_wrap(~ group)
```

**Frequently Used Arguments:**
- `~ group`: Faceting formula.
- `scales`: e.g. "free_y" for independent scales.

---

### theme()
**Description:**
Customizes non-data elements of a ggplot (text, backgrounds, grids).

**Usage:**
```r
ggplot(data, aes(x = var1, y = var2)) +
  theme(axis.text = element_text(size = 12))
```

**Frequently Used Arguments:**
- Various elements such as `axis.text`, `legend.position`, etc.

---

### ggsave()
**Description:**
Saves the last executed ggplot to a file.

**Usage:**
```r
ggsave(filename = "plot.png", width = 8, height = 6)
```

**Frequently Used Arguments:**
- `filename`: Output file name.
- `width`, `height`: Dimensions.
