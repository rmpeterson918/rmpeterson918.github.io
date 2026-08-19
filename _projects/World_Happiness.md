---
layout: page
title: World Happiness Report
description: Interactive R Shiny application exploring global happiness trends and predictors.
img: assets/img/happiness_preview.png
importance: 3
category: work
related_publications: false
---

## Project Overview
This project was based on the World Happiness Report. My partner and I narrowed our focus to a selection of factors and deployed our own pared-down version of their website. We built an interactive dashboard in R and Shiny to visualize and analyze factors influencing global happiness metrics across countries and regions. This was the final project for our data visualization class.


<div class="container-fluid px-0 my-4" style="width: 100% !important; max-width: 100% !important; min-width: 100% !important; clear: both !important; display: block !important;">
  <div class="d-flex justify-content-end mb-2">
    <a href="https://01a00e38-f0a3-81bc-e1f7-d0b99a1d661a.share.connect.posit.cloud/" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-outline-primary">
      <i class="fa-solid fa-arrow-up-right-from-square"></i> Open in New Tab
    </a>
  </div>
  
  <iframe
    src="https://01a00e38-f0a3-81bc-e1f7-d0b99a1d661a.share.connect.posit.cloud/"
    title="World Happiness Report Dashboard"
    width="100%"
    height="950"
    style="width: 100% !important; min-width: 100% !important; height: 950px !important; min-height: 950px !important; border: 1px solid rgba(0, 0, 0, 0.15) !important; border-radius: 8px !important; display: block !important;"
    frameborder="0"
    scrolling="yes"
    allowfullscreen>
  </iframe>
</div>
<div class="caption mt-2">
  <strong>Interactive Dashboard.</strong> Filter indicators, compare regional trends, and examine underlying predictors directly within the app above.
</div>

---

### Technical Implementation
* **Framework:** R Shiny, `plotly`, and `ggplot2`
* **Data Processing:** `dplyr` and `tidyr`
* **Deployment:** Containerized hosting via Posit / shinyapps.io
