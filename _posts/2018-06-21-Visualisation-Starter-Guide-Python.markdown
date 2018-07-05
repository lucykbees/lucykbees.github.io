---

layout: post
title:  "Visualising Categorical Data For Merchandisers"
description: "A look at ways to view cover in python data using seaborn & pandas"
date:   2018-06-21 18:10:11 +0100
keywords: data-science, learning

---

You can view the python code I used for my plots [here](https://www.kaggle.com/ucandotherobot/swarmplots-for-fashion-cover-data)

## The problem with categorical data..  

I recently was given a fashion data set for a presentation and was excited to start using my new python skills to create some beautiful plots for the content. 

However after about 30 minutes became quite stumped as to how to display the important KPI's I was aware that the audience would like to see. 

I had this large data set,  with some interesting metrics, and each metric can be split in a number of different ways. 

In the case of fashion we have Gender, Brands, Clothing Categories... 
Then we have the important metrics of units sold and units in stock.. 
But its also data across 4 weeks.. so can also be considered a time series.. 

## How do people visualise merchandising data? 

When I worked as a merchandiser over 5 years ago.. most of the data was visualised in table formats 
Maybe some conditional formatting in excel. 
But it was mostly endless lists of tables and figures to read through. 

Now five years on, in the era of data science,  I thought the industry have might progressed

So I did a little research. 

I started with my usual search topics "Visualisation stock and sales data"... "Visualisation cover data".. etc. but nothing suitable came up! 

I then went for an image search.. "merchandising dash boards".. then finally checked out blog posts on [Edited](https://edited.com/blog). 

<figure class="half">
    <a href="/images/edited1.png"><img src="/images/edited1.png"></a>
    <a href="/images/edited2.png"><img src="/images/edited2.png"></a>
    <figcaption>Images showing modern fashion sales data visulisations from edited blog.</figcaption>
</figure>

Edited's most recent blog post did reinforce the point for me that simple visuals are the most effective, 
But the blog often only explores one category for one metric at a time. 

But I didn't find an already great way to display the metric I was most interested in. 


## Cover 

Cover in merchandising is a quick way to work out sell through of an item, 

It is simply 

current stock / average weekly sales 

which gives you a quick estimate of how many weeks your stock will last or how well it is performing

It is a great way to normalise your data, as you might have 1000 sales but 100000 units of stock 

Which would take 100 weeks to get rid of.. 



## Swarm plots


The problem with just plotting cover in a bar chart, it that is doesn't show the distribution in the data set.
Its very often with sales data that you have a few individual items with extreme cover values. 
In normal data science techniques you want to filter them out..
But in real life for sales data these anomalies are your best and worst selling products 

Here I have firstly a plot of average sales - looking at this high level, you could jump to conclusions that the shoes category in the top performer

Below I have then have a plot of average cover (normalised with log) - you could again jump to conclusion about shoes, this time that is the worst performing


Finally we have the swarm plot 

In this plot each dot represents a line item,

Here you can see that shoes has a few items with high cover
And it also unmasks the average cover of the other categories

Now you can see that many clothing and bag items are over performing on cover


<figure>
	<a href="/images/swarm.png"><img src="/images/swarm.png"></a>
</figure>

Will do more on plotting this data in future posts.. 

Inspired by this excellent seaborn [documentation](https://seaborn.pydata.org/tutorial/categorical.html)


Main benefits of the swarm chart:

* It points me in a direction, rather then looking line by line through the data in a spread sheet. 

* It also helps you to consume more of the data at once, as you can see both trend of cover and the overall distribution of the cover by brand. 

* It stops you coming to generalised conclusions as you would with the bar chart, eg. For me this highlights that there are a few footwear brands with extremely high cover (worth investigating as new season) 
