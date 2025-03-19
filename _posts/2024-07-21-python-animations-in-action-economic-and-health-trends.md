---
layout: single
title: "Beyond Static Charts"
date: 2025-03-17
author: "Nikhil Singh"
excerpt: Animation explaining hidden relation b/w Wealth and Health!.
header:
  overlay_image: "./img/bg-python-animation.jpg"
  caption: "[**ClickerHappy**](https://www.pexels.com/photo/disney-mickey-mouse-standing-figurine-42415/)"
use_math: true
author_profile: true
toc: true
toc_label: "Contents"
toc_icon: "list"
classes: wide
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

  2. GDP per capita - original dataset
   
  | Country Name                           | Country Code | Indicator Name               | 2016             | 2017             | 2018            | 2019             | 2020             | 2021             | 2022             | 2023             |
  |----------------------------------------|--------------|------------------------------|------------------|------------------|-----------------|------------------|------------------|------------------|------------------|------------------|
  | Heavily indebted poor countries (HIPC) | HPC          | GDP per capita (current US$) | 893.010597521193 | 931.787880001889 | 968.18729528141 | 976.312547557857 | 959.181737577661 | 1040.03410722444 | 1100.34076496851 | 1231.81257022963 |
  | Channel Islands                        | CHI          | GDP per capita (current US$) | 55950.1485360363 | 55806.5709126142 | 60783.3533081111| 60568.1085272721 | 56785.9402392525 | 66912.1750054447 | 67627.3082341446 | 74589.1380225191 |
  | Barbados                               | BRB          | GDP per capita (current US$) | 19065.8069800213 | 19692.7606711615 | 20055.915870771 | 20583.7265786414 | 18347.1109131055 | 18696.7858952957 | 22164.0260273876 | 23804.0249914995 |

- **Python Libraries:**  
  - [Plotly](https://plotly.com/python/) for interactive animations  
  - [Pandas](https://pandas.pydata.org/) for data handling  

## Analysis (with code)

Check out the complete Python code 🔗 [here](https://github.com/nikhilsingh13/PythonHacks/blob/main/blog-work/python_animations/py-animation-gdp-lifeexp.ipynb).

## Conclusion

More insights coming soon!

---
