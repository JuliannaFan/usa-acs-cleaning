# USA ACS Cleaning Code

## My Code Files

The two R Markdown files in this repository are my code files:

- `clean_usa_00001.Rmd` cleans the 2016–2019 ACS extract.
- `clean_usa_00002.Rmd` cleans the 2021–2024 ACS extract.

My code creates these variables: `movedbtstates`, `state_specific`, `quasi_national`, `occupation`, `industry`, and `moved_50plus`.

## What My R Code Does

The code only keeps the columns needed for these variables. It also keeps the person ID columns, so the cleaned data can be matched with other group members' data later.

For jobs, the code uses the right occupation codes for each year. It also makes sure teachers work in elementary or secondary schools.

For moving, the code checks the person's current state, previous state, and moving status. For `moved_50plus`, it uses a map to calculate the straight-line distance between the old and new areas.

## Cleaned Variables

- `movedbtstates`: 0 = did not move to another U.S. state. 1 = moved to another U.S. state. NA = old location is outside the U.S. or missing.

- `state_specific`: 1 = one of the 16 state-specific licensed jobs. 0 = one of the six quasi-national licensed jobs. NA = other jobs or missing job information.

- `quasi_national`: 1 = one of the six quasi-national licensed jobs. 0 = other valid jobs. NA = missing job information.

- `occupation`: Current job code. Invalid or missing codes are NA.

- `industry`: Current industry code. Invalid or missing codes are NA. Teachers must have industry code 7860.

- `moved_50plus`: 0 = moved less than 50 miles. 1 = moved 50 miles or more. NA = old location is outside the U.S. or missing.
