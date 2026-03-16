- Does your proposal include all of the above mentioned sections? 1/1
- Are your objectives concrete and do you have a clear stakeholder need? 2/2

Nice

- Do you have a good data source and have you done a thorough job investigating its provenance and credibility? 1/1
- Did you do a thorough job exploring your data 2/2
- Have you done some initial modeling of your problem and do you have some early baseline results? 3/3

You might want to try to classify emp_title into a sector - that may indeed have an impact on loan default behavior; people who are starting businesses may be subject to more risk than those with stable employment. You could do a cluster analysis to see if different subsets of features correlate with the loan default.  I'm not so sure about state - you could certainly plot rates before you drop the feature.

Tree-based methods are likely going to do a bit better here. 

- Do you have a clear path forward 1/1

Nice work.  You probably want to do a little more exploration of your feature space, and probably try clustering to see if there are subgroups where defaults predominate.  This can inform feature selection or could even be input to a classifier.  Or you could calculate default rate per cluster in UMAP space, and then assign unseen (test) values to clusters and use this to calculate risk, or build per cluster classifiers.

I'm very curious to see how set up your risk model.  This seems like an important and unexplored aspect the project.

If you need more computational resources, let me know and I can get you an Azure instance.

Score: 10/10