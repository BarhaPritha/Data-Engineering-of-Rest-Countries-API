# ETL of Rest Countries API

## Dataset

REST Countries API with selected fields
https://restcountries.com/v3.1/all?fields=cca3,name,capital,continents,languages,area,borders,population,startOfWeek,timezones

Fields extracted: cca3, name.common, capital, continents, languages, area, borders, population, startOfWeek, timezones


## Transformations Applied

- Capitalized the fields **country names, capitals, continents, start of week, languages**.
- Converted the field **country code / cca3** to uppercase. 
- Computed **population density** = `population / area` (rounded to 2 decimals).  
- Flattened arrays/lists into comma-separated strings (`timezones`, `borders`, `continents`).  
- Normalized languages into a separate `languages` table.  
- Created a join table `country_languages` for many-to-many relationships.  
- Ensured type consistency:
  - `population` → integer  
  - `area` → float  
  - `density` → float  
- Handled missing values (`NULL` stored in SQLite).


## How to Run

Use a Python IDE to open and run the etl_task.py file.

OR 

Open a terminal or command prompt and enter the command `Python etl_task.py`.
