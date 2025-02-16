# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Jingkenh (Ken) Loh

## Stages of sampling:

### 1. Infect a random subset of people

**Sampling procedure:** Each person has a 10% chance of getting infected (*ATTACK_RATE = 0.10*). Each infected person is chosen randomly using *np.random.choice(ppl.index, size=int(len(ppl) * ATTACK_RATE), replace=False)*. 

**Function:** simulate_event(m)

**Sample size and sample frame:** Sample size is 1000, with the sample frame being 1000 people attending wedding and brunches (200 for weddings, 800 for brunches).

**Underlying distribution:** Discrete probability distribution, as we are randomly selecting a fixed number of people to be infected and each person has a fixed 10% chance of being infected.

**How it relates to the procedure outlined in the blog post:** We are using the same number of attendees for the same events as the blog post, which is 200 for weddings and 800 for brunches, with 10% of the people being infected.

### 2. Primary contact tracing: randomly decide which infected people get traced

**Sampling procedure:** each infected person has a 20% chance of being traced (*TRACE_SUCCESS = 0.20*). The code used to determine who gets traced is *ppl.loc[ppl['infected'], 'traced'] = np.random.rand(sum(ppl['infected'])) < TRACE_SUCCESS*.

**Function:** simulate_event(m)

**Sample size and sample frame:** Sample size is the number of infected people, and sample frame is all infected people who attended either a wedding or brunch.

**Underlying distribution:** Binomial distribution, as there are only two possible outcomes here of success or failure. The success rate is 20% for traced, and failure is 80% for untraced, in n independant trials.

**How it relates to the procedure outlined in the blog post:** The blog post also uses a probability of 20% for an infection being traced to a source event.

### 3. Secondary contact tracing based on event attendance

**Sampling procedure:** If at least two cases from the same event are traced, then all infected individuals at the event are assumed to be traced (*SECONDARY_TRACE_THRESHOLD = 2*). The code used for this is:

* event_trace_counts = ppl[ppl['traced'] == True]['event'].value_counts()
  events_traced = event_trace_counts[event_trace_counts >= SECONDARY_TRACE_THRESHOLD].index
  ppl.loc[ppl['event'].isin(events_traced) & ppl['infected'], 'traced'] = True*

**Function:** simulate_event(m)

**Sample size and sample frame:** The sample size is the number of individuals traced in the primary contact tracing step. The sampling frame is an event where at least two infected individuals were traced.

**Underlying distribution:** Conditional probability, as this describes the probability taht event A will happen given taht event B has already happened.

**How it relates to the procedure outlined in the blog post:** The blog post uses the same "secondary contact tracing" step, where if two infections are independently traced to the same source event, it is assumed that it will result in 100% of the infections associated with that event being identified. 

## Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

No, it does not reproduce it completely, as the 'Traced to Weddings' (red histogram) is not the same as the Observed proportion (red histogram) of the blog post, as the one in the blog post has a mean observed proportion around double the 'True proportion' (blue histogram). The code produces two histograms that are similar, with both being centred around the same proportion of cases, which is around 0.20, unlike the blog post.

## Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

The reproducibility of the results are poor when the number of repetitions in the simulation is set to 100, as the outputted graphs are different each time the script is run. 

## Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file.

I altered the code by adding a seed using *np.random.seed(m)* inside the function. This would make it produce the exact same output each time the script is run, which means it is completely reproducible. 

I used *np.random.seed(m)* inside the function instead of specifying a seed number as the function is being run 100 times in a range of 0-99 for m (*[simulate_event(m) for m in range(100)]*), which means it will just run the seed with the same number as the simulation. If a seed number is specified, each individual simulation would be exactly the same, and a histogram would not be produced.


## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 16/02/2025`
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [x] Create a branch called `assignment-1`.
- [x] Ensure that the repository is public.
- [x] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [x] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
