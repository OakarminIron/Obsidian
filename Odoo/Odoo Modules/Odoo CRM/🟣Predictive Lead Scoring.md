Predictive lead scoring is a machine-learning model that uses historical data from `Odoo` `CRM` to score open leads/opportunities.
As a company processes opportunities through the `CRM` pipeline, `Odoo` collects data on which opportunities are won and lost. 
Predictive lead scoring uses this data to predict the probability of winning each new lead or opportunity.
The more opportunities that are sent through the `CRM` pipeline, the more data `Odoo` collects, resulting in more accurate probabilities.
Specifically, `Odoo`’s predictive lead scoring uses the [[Naive Bayes]]:

Any number of the following variables can be activated:
- State: the geographical state from which the opportunity originates
- Country: the geographical country from which the opportunity originates
- Phone Quality: whether or not a phone number is listed for the opportunity
- Email Quality: whether or not an email address is listed for the opportunity
- Source: the source of an opportunity (e.g. search engine, social media)
- Language: the spoken language specified on the opportunity
- Tags: the tags placed on the opportunity