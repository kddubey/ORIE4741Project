# Building Permit Prediction

### Description of Project

As a homeowner, property developer, real estate agent, contractor, or investor it is often pertinent to perform alterations or to construct additional structures on your property. Whether the project is to renovate the front porch on your house or to construct a new guest-house in the backyard, cities require that a building permit be completed. A building permit is an official approval issued by the local government agency allowing you or a contractor to proceed with the construction or remodeling project. Permit approval follows the process of first being filed, then being issued, and finally, once all relevant work on the property is finished, completion.

Our aims in this project are to identify factors which affect whether a building permit will be issued, and how long it will take in days for a permit application to move from the fileing stage to the issued stage. Factors which will likely play a large effect are the type of proposed construction, the type of the required permit, the location or neighborhood in which the construction will occur, and the overall size of the project. It is reasonable to assume that smaller projects, such as ones where a landlord is doing a minor remodeling, will be approved much faster than a permit for construction of a large, new apartment complex. Other factors which are of interest to our project are local crime statistics, traffic patterns, and local mass-transit options surrounding the propsed construction site.

For this project data for building permit applications in New York City and San Francisco are being considered. The NYC dataset contains 3.6 million permit records and spans 14 columns [NYC Permit Data](https://data.cityofnewyork.us/Housing-Development/DOB-Permit-Issuance/ipu4-2q9a). Columns identify many important factors including location information, permit type, job type, and owner information in addition to the dates of fileing, issuing, and completion. The San Francisco dataset contains 200,000 permit records and spans 43 columns [SF Permit Data](https://www.kaggle.com/aparnashastry/building-permit-applications-data). Columns here include similar information as in the NYC data; however, the data is far cleaner and more consistently recorded. Our plan is to first investigate and develop models for the SF data, and then see if our model can generalize onto samples from the NYC dataset.

### Data Exploration

Looking at the distribution of permit statuses in the SF dataset, we see that the majority are either "completed", "issued", or "filed"; however, there are a total of 14 categories represented. Given that we are interested in predicting how long it will take a building permit to move from "filed" to "issued" or "completed", it is encouraging that there are many entries to work with.

![](Figures/histogram_permit_status.png)

When we look at the columns of "Filed date", "Issued date, and "Completed date" we see that 100% of all permits have been filed, 92.5% have been issued, and 48.9% have been completed. It is encouraging that all listed permit records have an issued date and the high proportion of permits which have been issued provides ample training data.

![](Figures/histogram_days_to_issue.png)

If we look closer, we see that 62.8% of all permits are issued on the same day that they were filed.

