Power BI can be used for data visualization.

First we need to import our data. In this case we are importing an Excel sheet. You have the option to transform the data first, such as renaming column names, removing rows, etc.
![powerbi](/img/powerbi.JPG)

Now you can create visualizations. You can choose different ones under "visualization". "Data" is where you select the columns that you want to use for your visualization.
![powerbi2](/img/powerbi2.JPG)

Power query allows you to make changes to your data before loading it in Power BI. You can do all the things you can do in Excel too like removing rows, updating column types, updating names, and filtering.

You can create relationships between different tables in Power BI. You can do that in the model tab. Power BI often creates relationships automatically but you are able to change those if you want.
![powerbi3](/img/powerbi3.JPG)

If you want to make edits to the relationship, you can do this by clicking on the line.
![powerbi4](/img/powerbi4.JPG)

### Using DAX (Data Analysis Expressions) in Power BI
Can be used to create measures or calculated columns in Power BI

To create a measure, you go to your data on the right of your screen and click on the three dots.
![powerbi5](/img/powerbi5.jpg)

When you click on the three dots, you can click on the option New Measure.
![powerbi6](/img/powerbi6.jpg)

Now you can create your new measure. You can create a formula like you could in Excel.
![powerbi7](/img/powerbi7.JPG)

SUMX is a function in Power BI that allows you to do calculations by row instead of summing up the whole column like the SUM function would do.

```
CALCULATION = SUMX(table, equation) 
```

### Using Drill Down in Power BI
In Power BI, you can create hierarchies and display that in your chart.

In this example, we have store and product on the x-axis and total price on the y-axis. In the first level of the hierarchy, we show the total price by store. However, we can look at the second level if we want which would be the total price by product by store. You can do this by using the drill down function by clicking on the downward facing arrow.
![powerbi8](/img/powerbi8.JPG)

When you click on that, you can click on any of the bars in the chart and it would then drill down to the next level.
![powerbi9](/img/powerbi9.JPG)
