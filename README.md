# Executive Summary

### Overview

<p>The objective of this project was to indicate the presence of West Nile Virus(WNV) for the city of Chicago. We used time, location and an feature-engineered mosquito count column to build a model to indicate the presence of the virus.</p>

<p>We conducted extensive research on the virus, mode of transmission, symptoms, treatments and some statistical information. These are summarized as follows:</p>

<ul>
    <li>Season - May through October</li>
    <li>Mode of transmission - Through the bite of an infected adult mosquito</li>
    <li>Symptoms             - Range from fever to death</li>
    <li>Statistics           - 1/5   show minor/non severe symptoms, 1/150 show severe/fatal symptoms</li>
</ul>

<p>We studied the lifycyle of a mosquito and concluded that it is easiest to terminate/control the population of mosquitoes during the egg,larvae and pupa life-cycle stages of mosquito. A statement released by EPA indicated the risk of aerial spraying range from low acute toxicity at lower concentrations to fatal/severe toxicity at higher concentrations.</p>

### Visualizations

<p>We used Matplotlib for more basic line charts, for instance the counts of each species over time:</p>

<p><img src="./images/species_count.png" /></p>

<p>We used Seaborn for heatmapping, for example, West Nile Virus presence in geographic zone per year:</p>

<p><img src="./images/mosquito_wnv_counts_2011-13.png" /></p>

<p>This data helped us to conclude that the ideal weather for spread of WNV through mosquitoes are periods of rain followed by humid weather and sunshine. Mosquitoes really thrive under this condition and we obtained a pretty high correlation when we saw similar trends in the weather.</p>

### Modeling

<p>To get an idea of what we were dealing with, it was useful to break the numbers out into a table:</p>

<p><img src="./images/row_counts.png" /></p>

<p>This allowed us to determine, at least for this project, that the recorded spray data was irrelevant since it occurred in off-years from the recorded mosquito counts and since pesticide is required by the EPA to break down in a biologically safe way within a short period of time. Also based on the clear imbalance in the count numbers, we bootstrapped our data to avoid bias.</p>

<p>The next step involved mapping out our workflow and fitting and scoring a regression model. We used the following regressor models and evaluated the cross validation scores to check the accuracy of the model using:</p>

<ul>
   <li>Bagging Regressor</li>
   <li>Random Forest Regressor</li>
   <li>Extra Trees Regressor</li>
   <li>ADA Boost Regressor</li>
</ul>

<p>We used the mosquito count from our regression problem as an engineered feature for our classification problems by moving the count into the dummied mosquito species columns. We then tried different classification models:</p>

<ul>
   <li>Random Forest Classifier
   <li>Extra Trees Classifier
   <li>Support Vector Classifier
   <li>ADA Boost Classifier
   <li>Logistic Regression Classifier
</ul>

<p>The highest accuracy in our Kaggle score was achieved through the Logistic Regression Classifier which came out to around 64%.</p>

### Conclusion

<p>As a part of our conclusions, we suggested the use of some alternative chemical pesticides. More specifically, bats have been shown to be extremely effective in controlling insect populations in Austin, TX and there are already 8 native bat species which populate the downtown Chicago area. Making the area more bat-friendly combined with a large-scale PR and education campaign could result in saved lives.</p>

<p>We finished our project by conducting some cost analysis and coming to a conclusion that aerial spraying must be used only we see a total number of 75 cases within the city of Chicago. This number was calculated keeping in mind ecological factors, effects on human beings and animals and cost factor.</p>