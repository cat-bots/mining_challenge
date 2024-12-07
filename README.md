# Issue Classification with ChatGPT Sharing Data

## Overview
This project analyzes issues shared by developers with ChatGPT to identify common categories of developer queries, such as bugs, feature requests, theoretical questions, and more. By classifying these issues, we aim to gain insights into how ChatGPT is used by developers and identify areas for improvement in addressing their needs.

## Objectives
1. **Classify developer issues:** Categorize prompts into predefined issue types such as `Bug`, `Feature Request`, `Theoretical Question`, etc.
2. **Identify trends:** Understand the types of issues developers frequently face.
3. **Refine categorization:** Reduce the number of `Uncategorized` prompts by adding new categories and refining keyword matching.

## Data Preparation
- All JSON files containing `issue_sharings` data were moved into a new directory called `issues_dir`.
- The JSON files were loaded and combined into a single DataFrame (`result_df`) for analysis.
- Nested structures in the JSON files were flattened using `pd.json_normalize` to facilitate classification.

## Issue Classification
A Python function, `classify_issue_type(prompt)`, was developed to classify prompts based on keyword matching. The current categories and their keywords are:

| **Category**              | **Keywords**                                                                                  |
|---------------------------|----------------------------------------------------------------------------------------------|
| **Bug**                   | bug, error, errors, issue, broken, failure, does not work, problem, problems                  |
| **Feature Request**       | feature, request, enhancement, add, include, create                                           |
| **Theoretical Question**  | how to, explanation, explain, define, describe                                                |
| **Performance/Optimization** | optimization, performance, improve, speed, faster, modify                                     |
| **Discussion/Question**   | question, discussion, debate, opinion, is it true, can I ask                                  |
| **School/Education**      | school, project, class, assignment, classmate, student, professor                             |
| **Thanks**                | thank you, thanks                                                                             |
| **Uncategorized**         | Prompts that do not match any of the above categories.                                        |

## Improvement Areas
The high count of `Uncategorized` prompts indicates potential for refinement. To address this:
1. Add new categories, such as `Debugging Assistance`, `API/Library Usage`, `Configuration/Setup Issues`, and more.
2. Expand existing keyword sets to capture variations in prompt phrasing.
3. Review a sample of `Uncategorized` prompts to identify recurring themes.

## Dependencies
- **Python Libraries:**
  - `pandas` for data manipulation
  - `json` for parsing JSON data
  - `matplotlib` for graphs
  - `googletrans` for translating prompts

## Next Steps
1. Refine keyword sets and add new categories to improve classification accuracy.
2. Perform trend analysis on classified data to identify developer pain points.
3. Develop visualizations to present findings.
