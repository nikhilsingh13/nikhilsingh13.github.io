---
layout: single
title: "Beyond Static Charts: Animation explaining hidden relation b/w Wealth and Health!"
date: 2025-03-17
author: "Nikhil Singh"
header:
  overlay_image: "./img/bg-python-animation.jpg"
  show_overlay_excerpt: false
use_math: true
toc: true
toc_label: "Contents"
toc_icon: "list"
---

# Python animations: enhancing data visualisations

Ever wondered if money could buy health? Well, it might not buy happiness directly, but it could add a few years to your life! In this post, we're diving into the interesting connection between a nation's wealth and its health.

I am going to use Python animations and World Bank data to show how closely the world's GDP correlates with life expectancy. Probably, we'll find some interesting patterns!

*`GDP per capita`* & *`Life Expectancy`* are correlated. While preparing these two datasets for the last 20 years (2003 to 2022), I discovered interesting inequalities, diminishing returns, and outliers.

Static charts often miss the small details or fail to share the complete story. Animations can help reveal those nuances.

*Do you know that in 2003, Luxembourg's GDP per capita was 8x India's, and by 2022, it was 12x? Yet, the life expectancy gap narrowed by 1.5 years.*

## Data & Tools

- **World Bank Datasets:**  
  - [Life Expectancy](https://data.worldbank.org/indicator/SP.DYN.LE00.IN)  
  - [GDP per Capita](https://data.worldbank.org/indicator/NY.GDP.PCAP.CD)

- **Data Manipulation:**  
  1. Life expectancy (birth) - original dataset

  | Country Name | Country Code | Indicator Name                          | 1960   | 1961   | 1962   | 2000   | 2001   | 2002   | 2003   | 2022   |
  |--------------|--------------|-----------------------------------------|--------|--------|--------|--------|--------|--------|--------|--------|
  | Dominica     | DMA          | Life expectancy at birth, total (years) | 59.026 | 59.949 | 61.741 | 72.693 | 71.713 | 72.340 | 71.438 | 72.981 |
  | Lithuania    | LTU          | Life expectancy at birth, total (years) | 69.847 | 70.103 | 69.095 | 70.909 | 71.220 | 71.571 | 72.020 | 75.793 |
  | Ecuador      | ECU          | Life expectancy at birth, total (years) | 53.364 | 53.895 | 54.401 | 72.839 | 73.240 | 73.613 | 73.975 | 77.894 |

- **Python Libraries:**  
  - [Plotly](https://plotly.com/python/) for interactive animations  
  - [Pandas](https://pandas.pydata.org/) for data handling  

## Analysis (with code)

Check out the complete Python code 🔗 [here](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/python_animations/py-animation-gdp-lifeexp.ipynb).

## Conclusion

More insights coming soon!

---

## Other Credits

- Background image by [ClickerHappy](https://www.pexels.com/photo/disney-mickey-mouse-standing-figurine-42415/)