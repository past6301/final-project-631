# An Analysis on the Impact of NATO Membership on Semiconductor Imports

## 1. Research Question

For my final project I decided to examine how NATO membership relates to the amount, in U.S. Dollar, countries import semiconductors. I became interested in learning about semiconductor trade after listening to a podcast on how the industry works. I found it fascinating how it is the backbone of most of todays innovations and yet it is hardly discussed outside of technical circles. Because of its importance to innovation and the technology supply chain, semiconductors are viewed as essential imports to many nations and therefore important for national security. It was this tie to national security that made me curious if NATO countries, which is the largest defensive alliance, have started working towards importing more semiconductors. This could potentially mean that NATO countries are focusing on importing semiconductor both to increase their economies and for national security reasons. This would have implication on Non-Nato countries as they might stuggle to increase the number of semiconductors they import.

## 2. Hypothesis

**Null Hypothesis (H₀):** NATO membership makes no difference in mean semiconductor import value. Any observed difference is completely due to chance

**Alternative Hypothesis (H₁):** NATO countries import a higher amount of semiconductors, in terms of the value in USD of these semiconductors, as compared to Non-NATO countries

## 3. Data Description

Because I was interested in examining NATO memberships impact on semiconductor imports I had to find two datasets. Once that contained which countires are members of NATO and one that contained data on the value of how much each country in the world imports (in USD) in semiconductors. I then created a combined dataset with a boolean int value that represented NATO membership (1 - NATO : 0 - Non-NATO). From there the only other values of interest in the original dataset were the Trade Value (how much was imported) and the Country. I then ended up also calculating the log of the trade value for each country to get trade value on a log scale. Countries such as the United States ($21.57B), Hong Kong ($16.22B), and China ($11.7B) were the largest importers. Below are links to the datasets used:

NATO Membership: https://www.worlddata.info/alliances/nato.php#google_vignette
Semiconductor Imports: https://oec.world/en/visualize/treemap?dataset=hs17&show=country&flow=import&product=2.8541&time=2024

## 4. Methods

Summarize how you analyzed the data:

* The test statistic for your permutation test
* How you simulated or resampled under the null hypothesis
* The metric(s) for which you created bootstrap confidence intervals
* Why the CLT does not apply to at least one metric

For my permutation test, I decided to use calculated the mean difference in Trade Value between NATO and Non-NATO countries. I did this for both the raw Trade Value and the Log Trade Value. I then bootstrapped the Mean Raw & Log Trade values. I also decided to try bootstrapping the median as well to see what the differences look like between raw and log trade values and because in this case the Central Limit Theorem (CLT) would not apply to the raw median. Because of the skew in my raw trade data, the CLT would not kick in because the CLT works by normalizing mean overtime. Since the data was so heavily skewed taking the median value does not result in it normalizng to the population. I then created confidence intervals for mean raw and log trade values for NATO and Non-NATO countries.

## 5. Results

The observed mean difference for the raw trade value was 1186950187.699 and for log trade value it was 1.641. The p-values from the permutation test were 0.0011 and 0.0001 respectivelky meaning under both variations, if we use a cut of of 0.05, we would reject the null hypthesis. Below are the confidence intervals for these trade values:

I am 95% confident that the mean import trade value of semiconductors for NATO countires is between $265,053,364.81 and $3,016,728,968.66.
I am 95% confident that the mean import trade value of semiconductors for Non-NATO countires is between $197,914,955.72 and $676,327,510.44.

I am 95% confident that the mean log import trade value of semiconductors for NATO countires is between 8.329731 and 8.860119.
I am 95% confident that the mean log import trade value of semiconductors for Non-NATO countires is between 6.747464 and 7.153637.

## 6. Uncertainty Estimation

I used 1000 resamples in my bootstrap analysis, this was simply because the machine I ran this on started to struggle with any more resamples than this. For my permutation tests I used 10,000 reruns. My raw permutation test maintained the right skew while the log permutation test was more normally distributed. The CI's for the raw trade values were interesting because the NATO range was quite large while the Non-NATO was significantly smaller.

## 7. Limitations

It is to far of a stretch to say that NATO membership causes higher semiconductor imports. While we were able to reject our null hypothesis this does not mean that we can infer our alternative hypothesis was true. There are alot of other factors that should be considered if further inference was to be done. For example, which countries build the chips? What if Non-NATO countires are the primary builder/exporters so they don't rely on imports since they can produce them domestically. What impact does a countries GDP, Population, or other Trade Agreements play on imports. These are all important questions, along with others not mentioned, that should be considered if a full analysis is to be done.

## 8. References

NATO Membership: https://www.worlddata.info/alliances/nato.php#google_vignette
Semiconductor Imports: https://oec.world/en/visualize/treemap?dataset=hs17&show=country&flow=import&product=2.8541&time=2024
