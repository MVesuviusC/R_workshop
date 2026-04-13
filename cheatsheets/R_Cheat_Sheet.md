# R Cheat Sheet

This document introduces you to the core building blocks of R. No programming background is needed—think of these concepts as the ways R stores and organizes information, similar to how you might use spreadsheets, filing cabinets, or simple lists in everyday life.

## Variable Structures in R (How Data is Organized)
- **Data Frame:**
  Think of this as a standard spreadsheet like Excel. It has rows (usually representing individual records, like patients or experiments) and columns (representing variables, like age, weight, or test results). Each column can hold a different type of information (for instance, one column can have text names, while another holds numeric ages).
- **Tibble:**
  A modern, upgraded version of a Data Frame. It works exactly like a spreadsheet but is more user-friendly. For example, if you have a massive dataset, a tibble won't accidentally print thousands of rows on your screen — it just shows you a neat, easy-to-read summary of the first few rows.
- **Vector:**
  A simple, one-dimensional list of items. Imagine a single column from a spreadsheet or a simple grocery list. Importantly, everything in a vector must be of the exact same type (e.g., all numbers or all text).
- **List:**
  A highly flexible container, acting like a filing cabinet drawer. Unlike a vector, a list can hold a mix of anything: numbers, text, entire data frames, or even other lists, all bundled together in a specific, ordered way. 
- **Matrix:**
  A two-dimensional grid of data (like a spreadsheet), but with a strict rule: *every single piece of data inside it must be of the exact same type* (usually numbers). It is almost entirely used for mathematical calculations under the hood.
- **Array:**
  Similar to a matrix, but it can have three or more dimensions. If a matrix is a flat piece of graph paper, an array is like a Rubik's Cube of data. You won't use these often unless you are doing advanced math or specific modeling.

## Data Types in R (The Kind of Information Stored)
- **Numeric:**
  The standard way R handles numbers. This includes any number—whole numbers or numbers with decimal points (e.g., `42`, `3.14159`, `-7.5`).
- **Factor:**
  A special and very useful way to store categorical data—data that falls into a specific, limited set of groups or categories. For example, "Low", "Medium", and "High", or "Control group" and "Treatment group". Factors help R know that these aren't just random words, but specific, comparable groups used for statistical analysis and graphical plotting.
- **Integer:**
  Strictly whole numbers without any decimals. In R, you rarely need to worry about the difference between integer and numeric for everyday tasks, but programmers sometimes use a special "L" suffix (like `10L`) to explicitly tell R "treat this exactly as a whole number."
- **Logical:**
  The simplest data type, representing boolean values: `TRUE` or `FALSE`. Think of it as a basic Yes/No switch in your data. It is heavily used when you want to filter things (e.g., checking "Is the patient older than 18? `TRUE` or `FALSE`").
- **Character:**
  Text data, which can be single letters, words, or entire paragraphs. In R, character data is always wrapped in quotation marks so R knows it isn't a command (e.g., `"Hello World"`, `"Patient A"`, `"Male"`).
- **Complex:**
  Numbers that include a fictional "imaginary" component (e.g., `2+3i`). As a beginner, you will almost certainly never use this unless you do complex engineering math.
- **Raw:**
  Used for storing raw machine bytes. You can completely ignore this one as a beginner.
