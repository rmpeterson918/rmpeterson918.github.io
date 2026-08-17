---
layout: page
title: Abortion, Female Genital Cutting/Mutilation, & Maternal Mortality
description: Intro to R Final Project exploring global health disparities
img: assets/img/MMRbox.png
importance: 1
category: work
related_publications: false
---

<div class="text-muted mb-4">
  <strong>Rebekah Peterson</strong> | Willamette University<br>
  <em>DATA 501: Foundations of Data Science with R</em> &bull; Dr. Zechariah Meunier &bull; December 8, 2025
</div>

---

## Introduction

With access to abortion healthcare under threat in the United States, I wanted to explore what kind of connection exists between access to abortion and maternal mortality rates. There are large disparities in maternal health outcomes worldwide; 99% of maternal deaths occur in developing nations (Nour, 2008). Despite high spending, women in the US face worse health outcomes at higher rates than other wealthy countries (Munira Z. Gunja, August 15, 2024). 

Using data from the Woman Stats Project (Codebook, 2025), my project began by looking at data on abortion access and maternal mortality rates worldwide. In the process of exploration, it seemed that there was another variable connected to increased mortality. This led me back to the Woman Stats Project, where I found data on female genital mutilation.

**Guiding Research Question:** What is the effect of access to abortion care, and the practice of female genital cutting/mutilation (FGC/M), on maternal mortality rates?

* **$H_0$:** Access to abortion care and female genital mutilation do not affect maternal mortality.
* **$H_A$:** Both access to abortion and female genital mutilation have an impact on maternal mortality rates.

---

## Methods

My explanatory variables are **abortion access** and **female genital cutting/mutilation (FGC/M)**. The response variable is the **maternal mortality rate (MMR)** (deaths per 100,000 live births per year).

Abortion access varies from safe and legal to illegal under all circumstances. In countries where abortion is legal, there can still be financial burdens or other limitations that restrict access. The data were assigned ordinal values from 0 to 4 based on Woman Stats Project criteria.

<p class="font-weight-bold mb-1"><strong>Table 1.</strong> <em>Abortion access classification scale (Woman Stats Project, 2025).</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-striped">
    <thead class="thead-light">
      <tr>
        <th class="text-center" style="width: 15%;">Score</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-center font-weight-bold">0</td>
        <td>Abortion is safe and legal and not imposed by the state on women (i.e. forced abortions are not an issue).</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">1</td>
        <td>Abortion is legal (although may not be available on demand for the asking), or there may be gestational age restrictions past the first trimester. The law may require parental permission or a waiting period.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">2</td>
        <td>Abortions may be restricted, but there are many reasons for permission to be given, including financial reasons. Spousal permission may also be required, or the permission of a physician’s committee, or gestational age restrictions may prohibit abortion prior to 12–13 weeks.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">3</td>
        <td>Abortions are severely restricted to cases where the life of the mother is at risk, possibly also rape and incest.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">4</td>
        <td>Abortions are illegal (also includes cases where states impose forced/coerced abortions on women).</td>
      </tr>
    </tbody>
  </table>
</div>

Female genital cutting/mutilation is the practice of cutting or completely removing the external genitalia. The dataset combined data on both legal and cultural acceptance of the practice into a single score ranging from 0 to 6.

<p class="font-weight-bold mb-1"><strong>Table 2.</strong> <em>Female genital cutting/mutilation (FGC/M) prevalence scale (Woman Stats Project, 2025).</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-striped">
    <thead class="thead-light">
      <tr>
        <th class="text-center" style="width: 15%;">Score</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-center font-weight-bold">0</td>
        <td>There is essentially no FGC/M and laws against the practice are strict, comprehensive, and enforced.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">1</td>
        <td>There is very little FGC/M, or laws may not be comprehensive or enforced well.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">2</td>
        <td>There is very little FGC/M and laws may not be comprehensive or enforced well.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">3</td>
        <td>FGC/M may be as high as 25% and laws may not be comprehensive or enforced well.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">4</td>
        <td>FGC/M may be as high as 50% and laws may not be comprehensive or enforced well.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">5</td>
        <td>FGC/M is highly prevalent and laws may not be comprehensive or enforced well.</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">6</td>
        <td>FGC/M is highly prevalent, and there are no laws banning the practice.</td>
      </tr>
    </tbody>
  </table>
</div>

For clarity on spatial visualizations, a second dataset was used to group MMR into scalar categories:

<p class="font-weight-bold mb-1"><strong>Table 3.</strong> <em>Maternal Mortality Ratio (MMR) scalar classifications.</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-striped">
    <thead class="thead-light">
      <tr>
        <th class="text-center" style="width: 15%;">Score</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-center font-weight-bold">0</td>
        <td>0–10 maternal deaths per 100,000 live births</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">1</td>
        <td>11–30 maternal deaths per 100,000 live births</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">2</td>
        <td>31–100 maternal deaths per 100,000 live births</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">3</td>
        <td>101–300 maternal deaths per 100,000 live births</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">4</td>
        <td>301+ maternal deaths per 100,000 live births</td>
      </tr>
    </tbody>
  </table>
</div>

---

### Statistical Assumptions & Testing

Before running regressions or significance tests, assumptions of normality and homoscedasticity were checked:

* **Shapiro-Wilk Test for Normality:** 
  * Abortion Access: $W = 0.83$, $p = 7.76 \times 10^{-13}$
  * FGC/M: $W = 0.80$, $p = 4.71 \times 10^{-14}$
  * Maternal Mortality Rate: $W = 0.69$, $p = 2.20 \times 10^{-16}$
* **Brown-Forsythe Test for Homoscedasticity:**
  * Abortion Access & MMR: $F = 8.24$, $p = 4.71 \times 10^{-6}$
  * FGC/M & MMR: $F = 5.60$, $p = 2.80 \times 10^{-5}$

Because variables violated normality and homoscedasticity, non-parametric tests were selected:

* **Kruskal-Wallis Tests:**
  * Abortion Access & MMR: $\chi^2 = 71.25$, $df = 4$, $p = 1.237 \times 10^{-14}$
  * FGC/M & MMR: $\chi^2 = 38.99$, $df = 6$, $p = 7.204 \times 10^{-7}$
* **Pairwise Wilcoxon Rank-Sum Tests:** Evaluated differences across individual scale levels (Tables 4 & 5).

<p class="font-weight-bold mb-1"><strong>Table 4.</strong> <em>Pairwise Wilcoxon rank-sum test p-values: Abortion Access and MMR.</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-bordered text-center">
    <thead class="thead-light">
      <tr>
        <th>Score</th>
        <th>0</th>
        <th>1</th>
        <th>2</th>
        <th>3</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="font-weight-bold">1</td>
        <td>1.0000</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">2</td>
        <td>1.0000</td>
        <td>0.2226</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">3</td>
        <td>0.1518</td>
        <td>2.00e-13</td>
        <td>0.0069</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">4</td>
        <td>0.1518</td>
        <td>4.80e-05</td>
        <td>0.1518</td>
        <td>1.0000</td>
      </tr>
    </tbody>
  </table>
</div>

<p class="font-weight-bold mb-1"><strong>Table 5.</strong> <em>Pairwise Wilcoxon rank-sum test p-values: FGC/M and MMR.</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-bordered text-center">
    <thead class="thead-light">
      <tr>
        <th>Score</th>
        <th>0</th>
        <th>1</th>
        <th>2</th>
        <th>3</th>
        <th>4</th>
        <th>5</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="font-weight-bold">1</td>
        <td>1.0000</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">2</td>
        <td>0.4634</td>
        <td>0.1610</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">3</td>
        <td>0.6729</td>
        <td>0.4634</td>
        <td>1.0000</td>
        <td>—</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">4</td>
        <td>0.4634</td>
        <td>0.1917</td>
        <td>0.4634</td>
        <td>0.3115</td>
        <td>—</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">5</td>
        <td>0.0679</td>
        <td>0.0008</td>
        <td>0.0020</td>
        <td>0.0049</td>
        <td>1.0000</td>
        <td>—</td>
      </tr>
      <tr>
        <td class="font-weight-bold">6</td>
        <td>0.4634</td>
        <td>0.0752</td>
        <td>0.4634</td>
        <td>0.4634</td>
        <td>1.0000</td>
        <td>1.0000</td>
      </tr>
    </tbody>
  </table>
</div>

**R Packages Utilized:** `tidyverse` (Wickham et al., 2019), `dplyr` (Wickham et al., 2023), `ggplot2` (Wickham, 2016), `maps` (Deckmyn, 2025), and `car` (Fox & Weisberg, 2019).

---

## Results

### Abortion Access & MMR

<div class="row my-4 justify-content-center">
    <div class="col-12 col-md-10 text-center">
        {% include figure.liquid loading="eager" path="assets/img/MMRbox.png" title="Figure 1: Distribution of Maternal Mortality Ratio across Abortion Access scale scores" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
    </div>
</div>
<div class="caption text-center mt-2 mb-4">
    <strong>Figure 1.</strong> 
</div>

<p class="font-weight-bold mb-1"><strong>Table 6.</strong> <em>Summary statistics of MMR across Abortion Access scale scores.</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-striped">
    <thead class="thead-light">
      <tr>
        <th class="text-center">Abortion Score</th>
        <th class="text-right">Min</th>
        <th class="text-right">Q1</th>
        <th class="text-right">Median</th>
        <th class="text-right">Q3</th>
        <th class="text-right">Max</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-center font-weight-bold">0</td>
        <td class="text-right">5</td>
        <td class="text-right">7.5</td>
        <td class="text-right">10.0</td>
        <td class="text-right">26.5</td>
        <td class="text-right">43</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">1</td>
        <td class="text-right">2</td>
        <td class="text-right">5.0</td>
        <td class="text-right">9.0</td>
        <td class="text-right">19.0</td>
        <td class="text-right">160</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">2</td>
        <td class="text-right">3</td>
        <td class="text-right">7.5</td>
        <td class="text-right">22.0</td>
        <td class="text-right">151.0</td>
        <td class="text-right">548</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">3</td>
        <td class="text-right">2</td>
        <td class="text-right">55.5</td>
        <td class="text-right">145.0</td>
        <td class="text-right">385.5</td>
        <td class="text-right">1,150</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">4</td>
        <td class="text-right">6</td>
        <td class="text-right">77.0</td>
        <td class="text-right">120.0</td>
        <td class="text-right">293.5</td>
        <td class="text-right">1,120</td>
      </tr>
    </tbody>
  </table>
</div>

The box plot and summary statistics (Figure 1, Table 6) illustrate the interaction between abortion access and MMR. There appears to be a marked increase in maternal deaths at scores of 3 and 4. Countries with a score of 0 or 1 have median mortality rates near 10 per 100,000 live births. Conversely, countries with scores of 3 or 4 have median mortality rates exceeding 100, with maximum values surpassing 1,100. 

In the pairwise Wilcoxon rank-sum test (Table 4), significant differences in medians emerged for score 1 versus scores 3 and 4, and for score 2 versus score 3. The small sample size of countries classified with a score of 0 explains why those differences were not statistically significant despite low absolute values.

---

### Female Genital Cutting/Mutilation & MMR

<div class="row my-4 justify-content-center">
    <div class="col-12 col-md-10 text-center">
        {% include figure.liquid loading="eager" path="assets/img/FGMbox.png" title="Figure 2: Distribution of Maternal Mortality Ratio across FGC/M prevalence scale scores" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
    </div>
</div>
<div class="caption text-center mt-2 mb-4">
    <strong>Figure 2.</strong> 
</div>

<p class="font-weight-bold mb-1"><strong>Table 7.</strong> <em>Summary statistics of MMR across FGC/M prevalence scores.</em></p>
<div class="table-responsive my-3">
  <table class="table table-sm table-hover table-striped">
    <thead class="thead-light">
      <tr>
        <th class="text-center">FGC/M Scale</th>
        <th class="text-right">Min</th>
        <th class="text-right">Q1</th>
        <th class="text-right">Median</th>
        <th class="text-right">Q3</th>
        <th class="text-right">Max</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="text-center font-weight-bold">0</td>
        <td class="text-right">4</td>
        <td class="text-right">4.75</td>
        <td class="text-right">7.0</td>
        <td class="text-right">21.25</td>
        <td class="text-right">58</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">1</td>
        <td class="text-right">2</td>
        <td class="text-right">5.00</td>
        <td class="text-right">8.0</td>
        <td class="text-right">67.00</td>
        <td class="text-right">548</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">2</td>
        <td class="text-right">2</td>
        <td class="text-right">17.00</td>
        <td class="text-right">60.0</td>
        <td class="text-right">173.00</td>
        <td class="text-right">1,150</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">3</td>
        <td class="text-right">3</td>
        <td class="text-right">17.00</td>
        <td class="text-right">46.0</td>
        <td class="text-right">121.00</td>
        <td class="text-right">829</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">4</td>
        <td class="text-right">53</td>
        <td class="text-right">136.25</td>
        <td class="text-right">415.5</td>
        <td class="text-right">729.50</td>
        <td class="text-right">917</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">5</td>
        <td class="text-right">37</td>
        <td class="text-right">301.25</td>
        <td class="text-right">440.5</td>
        <td class="text-right">591.75</td>
        <td class="text-right">1,140</td>
      </tr>
      <tr>
        <td class="text-center font-weight-bold">6</td>
        <td class="text-right">29</td>
        <td class="text-right">67.50</td>
        <td class="text-right">369.5</td>
        <td class="text-right">639.25</td>
        <td class="text-right">1,120</td>
      </tr>
    </tbody>
  </table>
</div>

The story is very similar when looking at female genital cutting/mutilation. In countries where it is both illegal and uncommon, the median mortality rate is close to zero. In countries where FGC/M happens at rates of 50% and higher (scores of 4 to 6), the median mortality rate exceeds 300 deaths per 100,000 live births. 

In the pairwise Wilcoxon rank-sum test (Table 5), there was a significant difference in median deaths between countries with a score of 5 and those with scores of 1, 2, and 3. There are very few countries with scores of 0 or 6 (10 altogether), explaining why the comparison between extreme bounds is not statistically significant.

---

### Geographic Distribution & Spatial Comparisons

To identify which countries have the lowest or highest MMR, scores were mapped onto a global heat map. Figure 3 supports Nour’s statement that 99% of maternal deaths occur in developing nations (Nour, 2008).

<div class="row my-4 justify-content-center">
    <div class="col-12 col-md-10 text-center">
        {% include figure.liquid loading="eager" path="assets/img/MMRmap.png" title="Figure 3: Global heat map of raw Maternal Mortality Ratio" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
    </div>
</div>
<div class="caption text-center mt-2 mb-4">
    <strong>Figure 3.</strong> 
</div>

Because raw values compress variance under 300 deaths, the scaled MMR dataset was mapped in Figure 4 to illustrate variation among countries with low baseline mortality. Australia and most of Europe demonstrate very low MMR (< 30), whereas South Sudan and Chad exceed 1,100 deaths per 100,000 live births.

<div class="row my-4 justify-content-center">
    <div class="col-12 col-md-10 text-center">
        {% include figure.liquid loading="eager" path="assets/img/MMRscaleMap.png" title="Figure 4: Scaled geographic mapping of Maternal Mortality Ratio" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
    </div>
</div>
<div class="caption text-center mt-2 mb-4">
    <strong>Figure 4.</strong> 
</div>

Comparing Figures 5 and 6 against Figure 4 shows clear spatial correlation: countries with deeper blue tones in Figure 4 consistently align with deeper blue tones in Figures 5 and 6.

<div class="row my-4 g-3 align-items-center">
    <div class="col-12 col-md-6 text-center">
        {% include figure.liquid loading="eager" path="assets/img/ABOmap.png" title="Figure 5: Global abortion access scale scores" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
        <div class="caption text-center mt-2">
            <strong>Figure 5.</strong> 
        </div>
    </div>
    <div class="col-12 col-md-6 text-center">
        {% include figure.liquid loading="eager" path="assets/img/FGMmap.png" title="Figure 6: Global FGC/M prevalence scale scores" class="img-fluid rounded shadow-sm mx-auto d-block" zoomable=true %}
        <div class="caption text-center mt-2">
            <strong>Figure 6.</strong> 
        </div>
    </div>
</div>

Notable outliers include China and Poland, which report restrictive abortion scores of 4 and 3 but low MMRs of 29 and 2. In China, this divergence may be explained by the legacy of state-mandated reproductive policies. For Poland, geographic proximity to European neighbors with safe, accessible abortion services likely mitigates national restrictions.

---

## Discussion

Both abortion care access and female genital mutilation have a clear association with maternal mortality rates. The more restrictions placed on abortion access, the higher a country’s maternal mortality rate is likely to be. Similarly, where female genital cutting is prevalent, mortality rates rise sharply. 

The combination of restrictive abortion policies and high FGC/M prevalence is particularly severe. In Chad, an abortion score of 3 and an FGC/M score of 5 coincide with a maternal mortality rate of 1,140 deaths per 100,000 live births. In contrast, countries reporting fewer than 10 deaths per 100,000 live births consistently maintain abortion and FGC/M scores of 2 or lower.

Maternal health outcomes are shaped by a broad spectrum of determinants, including access to prenatal care, adequate nutrition, baseline poverty, age at first birth, and contraceptive access (Women Still Face Big Gaps in Access to Health Care, 2013; Eyeberu et al., 2022). Furthermore, cross-sectional evaluation across a single year (2020) limits longitudinal causal inference.

Nonetheless, both abortion access and protections against FGC/M represent actionable societal factors. Expanding reproductive healthcare access and eliminating FGC/M practices through enforced legal protections remain critical pathways to improving maternal survival and broader public health (Grossi, 2024).

---

## References

* **Addis Eyeberu, T.** (2022). Teenage pregnancy and its predictors in Africa: A systematic review and meta-analysis. *NIH National Library of Medicine*. [PMC9682880](https://pmc.ncbi.nlm.nih.gov/articles/PMC9682880/)
* **Codebook.** (2025, September). *Woman Stats Project*. [womanstats.org](https://womanstats.org/new/codebook/)
* **Deckmyn, R. A.** (2025). *maps: Draw Geographical Maps* (R package version 3.4.3). [CRAN](https://CRAN.R-project.org/package=maps)
* **Fox, J., & Weisberg, S.** (2019). *An R Companion to Applied Regression* (3rd ed.). Sage.
* **Grossi, G.** (2024, August 15). US Women Face Worst Health Access, Outcomes Among High-Income Nations. *AJMC*. [Article Link](https://www.ajmc.com/view/us-women-face-worst-health-access-outcomes-among-high-income-nations)
* **Munira Z. Gunja, R. M.** (2024, August 15). Health Care for Women: How the U.S. Compares Internationally. *The Commonwealth Fund*.
* **Nour, N. M.** (2008). An Introduction to Global Women's Health. *Reviews in Obstetrics & Gynecology*, 33–37.
* **Partners in Health.** (2013, March 8). *Women Still Face Big Gaps in Access to Health Care*. [pih.org](https://www.pih.org/article/women-still-face-big-gaps-in-access-to-health-care)
* **Wickham, H. et al.** (2019). Welcome to the tidyverse. *Journal of Open Source Software*, 4(43), 1686.
* **Wickham, H. et al.** (2023). *dplyr: A Grammar of Data Manipulation* (R package version 1.1.4). [CRAN](https://CRAN.R-project.org/package=dplyr)
* **Wickham, H.** (2016). *ggplot2: Elegant Graphics for Data Analysis*. Springer-Verlag New York.
