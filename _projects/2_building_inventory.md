---
name: Building Inventory Dataset (Homework 5)
tools: [Python, HTML, vega-lite]
image: assets/pngs/hw5.png
description: Visualizations for the Illinois building inventory dataset.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Building Inventory Visualizations

## Plot 1: Total building area by agency

<vegachart 
    schema-url="{{ site.baseurl }}/assets/json/hw5_plot1_top10_agency_building_area.json"
    style="width: 100%">
</vegachart>

### Plot 1: Description
- This visualization summarizes the top ten Illinois state agencies based on the total building area they manage. Each bar represents one agency, with bar height encoding the total square footage across all buildings in the dataset. 
- It provides a picture of which agencies oversee the largest real estate and helps reveal differences in the scale of facility management responsibilities across government sectors.
- For encodings, I used a nominal x-axis for the agency names and a quantitative y-axis for total square footage. The bars are sorted in descending order to make comparisons easier, and each bar has a distinct categorical color. 
- Tooltips add detail by showing the exact square-footage value on hover. 
- I removed records missing square-footage values and aggregated totals  before selecting the top ten agencies to reduce clutter.

---

## Plot 2: Buildings constructed over time by usage categories

<vegachart 
    schema-url="{{ site.baseurl }}/assets/json/hw5_plot2_buildings_constructed_per_year_per_usage.json"
    style="width: 100%">
</vegachart>


### Plot 2: Description
- This visualization displays how many buildings were constructed each year by usage categories (such as Office, Storage, Educational, etc). 
- The x-axis encodes the construction year, while the y-axis shows how many buildings in the dataset were built during that year.
- For encodings, I use a ordinal x-axis (Year Constructed), a quantitative y-axis for the count of buildings, and a nominal color encoding for the usage category. 
- I filtered out missing or unrealistic years, standardized usage categories, and aggregated counts per year and category using groupby.
- The main interactive component is a dropdown menu that allows users to filter the plot by usage category.


<div class="left">
{% include elements/button.html 
   link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" 
   text="The Data" %}
</div>

<div class="right">
{% include elements/button.html 
   link="https://github.com/TejasHonmode/TejasHonmode.github.io/blob/main/python_notebooks/hw5.ipynb" 
   text="The Analysis" %}
</div>
