# English-Dictionary
A pandas project whicht processes a dictionary dataset, cleans it, and provides a command-line interface for looking up word definitions.

Here's a step-by-step breakdown of what the project does:


Import pandas: The first cell imports the pandas library, which is essential for working with DataFrames and performing data manipulation tasks.

Load the dataset: The second cell reads the "dict.csv" file into a pandas DataFrame named df. This is the initial step to load the raw data for processing.

Print the DataFrame: This cell simply displays the entire contents of the df DataFrame to give an overview of the data.

Check for missing values: This cell uses pd.isna(df) to check for any missing values (represented as NaN) in the DataFrame. The output shows a boolean DataFrame indicating whether each element is NaN or not.

Data cleaning and transformation: This cell performs several cleaning and transformation steps:
  It creates a copy of the original DataFrame df and names it df2 to avoid modifying the original data.
  It ensures that the 'word' column is of string type using .astype(str).
  It converts all words in the 'word' column to lowercase using .str.lower() to handle potential case inconsistencies.
  Finally, it displays the modified df2 DataFrame.

Sort and re-index: This cell sorts the df2 DataFrame alphabetically based on the 'word' column in ascending order using sort_values(). It then resets the index of the DataFrame using reset_index(drop=True, inplace=True) to have a clean integer-based index. The sorted and re-indexed DataFrame is then displayed.

Descriptive statistics: This cell generates descriptive statistics for all columns in the df2 DataFrame using describe(include='all'). This provides information like the count of non-null values, number of unique values, the most frequent value, and its frequency for each column.

Count word occurrences: This cell uses value_counts() on the 'word' column of df2 to count how many times each unique word appears in the dataset. This helps identify duplicate word entries.

Filter for a specific word: This cell demonstrates how to filter the DataFrame to find rows where the 'word' column is 'lead'. It displays the filtered rows and their data types. This is an example of how to access specific data based on a condition.

Remove duplicate words: This cell creates a new DataFrame df3 by dropping duplicate rows based on the 'word' column using drop_duplicates(subset='word', keep='first'). This keeps only the first occurrence of each unique word. It then resets the index of df3 and displays its descriptive statistics to show the effect of removing duplicates.

Count unique word occurrences: This cell counts the occurrences of each unique word in the cleaned df3 DataFrame using value_counts(). As duplicates were removed, each word should now appear only once.

Save the cleaned data: This cell saves the processed and cleaned df3 DataFrame to a new CSV file named "Dictionary.csv" using to_csv(). It also displays the df3 DataFrame.

Word lookup interface: This final cell provides a simple command-line interface for the user to look up word definitions. It prompts the user to enter a word, filters the df3 DataFrame to find the definition, and prints the definition if the word is found. If the word is not found, it displays a "Word not found" message. The loop within the if statement is designed to print the definition character by character, adding a newline after each period.


In summary, this project takes a raw dictionary dataset, cleans it by handling duplicates and casing, and provides a basic way to look up definitions from the cleaned data.
