# Assignment: Questionnaire Design and Sample Evaluation

## Requirements

The goal of this assignment is to practice developing and evaluating sampling materials.

### Part A - Survey Design:

Select one of the scenarios below and design a survey to meet the need(s) outlined in the prompt.

1.	In two to three sentences, describe the purpose of your survey
2.	Describe your target population, sampling frame, sampling units, and overall sampling strategy.
3.	Write a 5-10 question survey to address your chosen scenario below.

##### Scenarios
1.	You work in the Human Resources Department at a large tech company. Over the past few months, the company has been experiencing a high turnover rate across many of its departments, specifically within the entry- and lower-level positions. The company wishes to understand why this turnover is happening, and what changes need to occur to improve employee satisfaction.
2.	You work for a Canadian national political party during a federal election. Throughout the campaign period, your party has seen relatively high approval ratings, but an opposing party is also polling favorably and may still have a chance to win the election. You are one month away from the election and you want to understand what voters want from your party and its leader in order to maintain your lead and eventually win the election.
3.	You are a student researcher in the sociology department at the University of Toronto. You are working on a research project that concerns the relationship between music taste and age. This involves both comparisons between different people of different ages and comparisons of the same individual at different ages during their lifetime. You wish to understand to what extent age influences music taste, specifically as it relates to perceptions of popular music. Your results will be written into an academic paper that you hope to publish.

### Part B - Survey Evaluation:

For the **Canadian General Social Survey on Giving, Volunteering, and Participating, 2018 (cycle 33)**, conducted by Statistics Canada find any and all available documentation for the data gathered and identify and describe the survey features indicated below.

1. Sample type
2. Sample size
3. Target population
4. Sampling frame
5. Survey mode(s) 
6. Timeline
7. Response rate
8. Weights
9. Data processing
10. Cleaning, imputation, etc
11. Sources of error
12. Limitations, known biases, etc
13. Link to documentation and any additional sources used


# Your Changes

## Part A - Survey Design: 

The number of your chosen topic: `1`

Describe the purpose of your survey:
```
The purpose of my survey is to identify the reasons behind the high employee turnover rate across entry- and lower-level positions at the company. 
By gathering insights on why this high turnover is happening, we can then develop strategies to improve retention.
```

Describe your target population, sampling frame, sampling units, and observational units:

**Target population:** 
Current and recently departed employees who were in entry- and lower-level positions within the last 24 months.

**Sampling frame:** 
A list of employees from company records.

**Sampling units:** 
Current and former employees in entry- and lower-level positions.

**Overall sampling strategy:** 
The overall sampling strategy we will use is stratified random sampling, as it ensures that each department is represented since high turnover
has been occurring across multiple departments. This strategy also accounts for different employment statuses, such as current and former employees. We will also inform survey 
participants that they will remain anonymous in order to encourage honest responses.
We will divide the population by department, employment status, and tenure, then select a random sample from each group.


Your 5-10 question survey:
```
1. What is your current employment status?
[ ] Still employed at the company
[ ] Resigned within the past 6 months
[ ] Resigned within the past 12 months
[ ] Resigned within the past 24 months

2. What were the main factors that led you to leave or consider leaving the company? (Select up to three)
[ ] Low salary 
[ ] Limited career advancement
[ ] Poor work-life balance
[ ] Not enough benefits
[ ] Lack of support
[ ] Unclear or unrealistic job expectations
[ ] Workplace environment
[ ] Other (please specify): ____________

3. Did the company meet your expectations regarding professional development and career growth?
[ ] Exceeded expectations
[ ] Met expectations
[ ] Somewhat met expectations
[ ] Did not meet expectations

4. On a scale of 1 to 5, how satisfied were you with: (1 = Very Unsatisfied, 5 = Very Satisfied)
* Compensation & Benefits: 1 2 3 4 5
* Career Growth Opportunities: 1 2 3 4 5
* Work-Life Balance: 1 2 3 4 5
* Management Support: 1 2 3 4 5
* Workplace Culture: 1 2 3 4 5

5. Did you have enough resources and support to perform your job effectively?
[ ] Yes
[ ] Sometimes
[ ] No

6. Was your workload manageable?
[ ] Yes
[ ] Sometimes
[ ] No

7. What is one thing that would have encouraged you to stay longer at the company? You may provide more than one reason.
______________________________________________________________________________________________________________________

```

## Part B - Survey Evaluation:

Identify and describe survey features:


1. **Sample type:** 
The sample survey is a cross-sectional design, which looks at data at a specific point in time. In this case, the survey collects data only during the survey 
period from September to December. The sample is based on a stratified design employing probability sampling, with stratification done at the province/Census Metropolitan
Area level, which is how the sample is drawn from the population. This means that the population is divided into strata based on provinces and Census Metropolitan Areas to
ensure a representative selection of the population.

2. **Sample size:** 
50,000
There was a field sample of approximately 50,000, with 40,000 among them being invitation letters sent to selected households across Canada for the electronic questionnare,
with a completion of 24,000 questionnaires expected.

3. **Target population:** 
All persons 15 years of age and older living in the ten provinces of Canada, excluding full-time (residing for more than six months) residents of 
institutions.

4. **Sampling frame:** 
The survey uses a sampling frame that combines landline and cellular telephone numbers from the Census and various administrative sources with Statistics
Canada's dwelling frame.

5. **Survey mode(s):** 
Data are collected directly from survey respondents either through an electronic questionnaire or through computer-assisted telephone interviewing.

6. **Timeline:** 
Data collection for this period was from September 4, 2018 to December 28, 2018.

7. **Response rate:** 
41.9%

8. **Weights:** 
WGHT_PER, which is the basic weighting factor for analysis at the person level, i.e. to calculate estimates of the number of persons (non-institutionalized 
and aged 15 or over) having one or several given characteristics.

Survey estimates are adjusted using weights to ensure they are representative of the target population in terms of age, sex, and province.

Bootstrap weights were created for the purpose of design-based variance estimation, which allow for more precise calculations of sampling variability across different estimates.

Weights were also adjusted to account for non-response and to match the 2017 CIS income distribution by province.

9. **Data processing:**
Processing used the Social Survey Processing Environment (SSPE) set of generalized processing steps and utilities to allow subject matter and survey support staff to specify and run 
the processing of the survey in a timely fashion with high quality outputs.

It used a structured environment to monitor the processing of data ensuring best practices and harmonized business processes were followed.

SPPE is a standardized system that helps efficiently clean, validate, and process data while ensuring accuracy, consistency, and adherence to best practices.

10. **Cleaning, imputation, etc:**
All imputations were made using donor records selected through a score function. Where donor imputation could not be used, mean imputation among a pool of donors was used.

This means that missing data was filled by comparing records with similar characteristics, and the closest match (highest score) was used to replace missing values. If multiple
records had the same score, one was randomly selected. If imputation wasn't possible, mean imputation was used.

Imputation was carried out in nine steps. The first step consisted of imputing personal income and family income. The next three steps involved imputing the formal volunteering 
variables in the master file. Steps five and six were imputing the informal volunteering variables in the master file. The last three steps involved imputing variables 
in the donation file and the solicitation methods in the master file.

The GVP imputation process helped to fill incomplete responses with the experience of other respondents with similar or identical characteristics. For example, this was used
to fill in gaps in income data.

11. **Sources of error:**
Common sources of errors were imperfect coverage and and non-response. Coverage errors arise when there are differences between the target population and the
surveyed population. Non-response could occur at both the household and individual levels.

Other types of non-sampling errors included response errors and processing errors.

12. **Limitations, known biases, etc:**
Households without telephones were excluded from the survey population, which may introduce bias. Non-response bias was addressed through adjusting the survey weights.

13. **Link to documentation and any additional sources used:**
The General Social Survey: An Overview

## Rubric

-	All required components are present and complete **Complete / Incomplete**
-	Choice of sampling strategy for Part A is justified and related to survey purpose **Complete / Incomplete**
-	Information for Part B is complete and correct **Complete / Incomplete**

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 23/02/2025`
* The branch name for your repo should be: `assignment-2`
* What to submit for this assignment:
    * This markdown file (a2_survey_design_and_evaluation.md) should be populated and should be the only change in your pull request.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [x] Create a branch called `assignment-2`.
- [x] Ensure that the repository is public.
- [x] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [x] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
