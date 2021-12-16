# Project 3: Predictive modeling

You will use the same data provided by Databox that you have used in project 2. Data can be found [here](https://classroom.github.com/a/lNCqrUm1) and [here](https://drive.google.com/file/d/1xlBq18Ljh9fZ_o_KXaFuMe4fId9waS3G/view?usp=sharing).


## Databox SignupsAttributes.csv

**Please, note:** Some parts of the description (in bold) changed from project 2 to better describe the meaning of each attribute.

Data set includes data about a subset of customers:

| Attribute | Description |
| --------- | ----------- |
| $distinct_id | Customer id (identical to space_id) |
| $properties.space_id | Unique customer id |
| $properties.country | Country of the company in the system |
| $properties.is_agency | Company is an agency - true/false |
| **$properties.company_created** | **Timestamp when company when the company signed-up via webapp or undefined (empty)** |
| **$properties.became_paying** | **Timestamp when company became paying (it stays set even if company downgrades) or undefined** |
| **$properties.became_pql** | **Timestamp when company was categorised as PQL (product qualified lead) or undefined** |
| **$properties.cancelled** | **Timestamp when company downgraded back to the free plan or undefined** |
| $properties.had_trial | Company used the trial option - true/false |
| $properties.trial_features | List of trial features used - values separated with ; |
| **$properties.is_activated** | **True if company successfully connected a data source - true/false** |
| $properties.level_achieved | Onboarding level achieved - number |
| **$properties.has_mobile_company** | **Company logged into mobile app at least once - true/false** |
| $properties.sessions_company | Sessions count - number |
| $properties.databoards_company | Databoards count - number |
| $properties.cloud_sources_company | Cloud sources count - number |
| $properties.metrics_company | Number of Metrics added - number |
| $properties.users_in_space | Number of users added to space - number |
| $properties.scheduled_snapshots_company | Number of scheduled snapshots - number |
| $properties.custom_queries_company | Number of custom queries created - number |
| $properties.scripts_company | Number of scripts used - number  |


**Please note that value `undefined` means that the data was not set (empty).
All the counts represent the current state at the time of the export.**


## Databox AllEvents.csv

Dataset `AllEvents.csv` combines event data for 6 different events for 2 years. Since the file is large, we provided separate dataset per event type for your convenience. All datasets have the same structure, but not all datasets have a header.

List of files:
* AllEvents.csv (includes data from all files below)
* CalculationCreated.csv
* MetricAdded.csv
* NewDatasourcesAdded.csv
* QueryCreated.csv
* Sessions.csv
* ShareUrl.csv
* SnapshotShared.csv
* UsersAdded.csv


| Attribute | Description |
| --------- | ----------- |
| Date | Date of event in format yyyy-mm-dd |
| Event | Type of the event - string, may include some special characters |
| Space | Customer id | Id of the customer triggering event |
| Event_count | Number of events on the specific date |


## Instructions

You should use the knowledge, understanding, and preprocessing of data gained in project 2 to build a few predictive models that provide actionable results. For example, their predictions could be used to improve Databox's business directly. By understanding why a model works well and when does it fail, we could gain new knowledge and plan further improvements in the data collection and modeling.

Here are some questions you may want to answer (pick at least two, and, of course, you can identify and answer your own questions):

* Can we predict the probability of each customer to become paying in the next month (30 days)?
* Which attributes have the biggest impact on the customer becoming paying in the next month (30 days)?
* Can we predict the probability of every paying customer to become non-paying (downgrade to free account)?
* Which attributes have the biggest impact on the customer becoming non-paying in the next month (30 days)?
* Can we predict the number of new signups in the next month, 3 months, 6 months and a year?
* Can we predict the number of new paying customers in the next month, 3 months, 6 months and a year?


When thinking about "customer" you should think in the context of a `Space` and `Space_id`.

When modeling, evaluating and thinking about the above questions, you should be clear what data (attributes) are actually available at the time of prediction in a real-life business situation.

As a data scientist, your main task is to provide insights into the data to the reader by using predictive modeling. Importantly, you should estimate the expected predictive performance on new examples and select the best predictive model for each type of outcome you want to predict. You should try to identify the most important attributes for the prediction task. Also, you should try to explain why (and when) the model performs well and when does it fail. Aim for a concise, efficient, and effective solution.

In doing so, you should:

* Be careful on which data you train and test your models. For example, split the data into a training and a test set by selecting an arbitrary point in time to divide the two (*i.e.*, a rolling time window approach in case of temporal data).
* What measure(s) of predictive performance should you use?
* What are the costs associated with different prediction errors? How should they be reflected in the predictive performance measure that you will use to rank the various predictive models?
* What is the reference (baseline) performance that your best models should improve on?
* **Build and evaluate models to predict** a selected outcome.
* Report the predictive performance scores obtained.
* Based on the evaluation, propose the best models to be used in "production."
* Discuss other (practical) considerations when selecting the best model that should be used in "production."
* Depending on the learning algorithm used, you may not be able to use the entire data set. Use appropriate data sampling methods (be careful not to ignore the temporal component when sampling).
* Discuss why and when models perform well, and why and when they fail.

During the analysis you should also:

* Implement dynamic reports and provide all the code with instructions for your code to be reproducible.
* Produce appropriate visualisations of your results that are aesthetic, make sense and are without major technical flaws. Comment and discuss your work.

**Focus on quality, not quantity!** If you believe you cannot find appropriate solutions, justify and discuss that in the report.

In the report, you should describe your insights into the modeling and the obtained models to the reader through text, tables, and visualisations.

Submit your work within the assignment repository and organise it sensibly (code, visualisations, reports in separate folders). Along with the dynamic reports and source code you should also submit a short PDF 3-4 pages analysis report. In the README.md of your repository explain the structure of your files within the repository and also provide all the instructions to reproduce your work.


## Expected results

- Fully implemented and reproducible Jupyter notebook (predictive_modeling.ipynb)
- Short report, 3-4 pages PDF, use template. Please, name your report IDS2021-P3report_Name_Surname.pdf.
