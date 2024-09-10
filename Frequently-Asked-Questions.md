# Frequently Asked Questions

For now, this is a working document aggregating all of the questions we get from our trial period. We will begin merging similar questions together and organizing them into categories as we go. 

1. How do you know beforehand when to take insulin? Especially on times where you are forced to go off schedule, such as traveling on flights? Is it mostly instinct, or can you somehow predict beforehand when and how your BGL will fluctuate?

**Answer:** Great question! There's not much instinct at all! There are a few similar ways of doing this that depend on the method of insulin delivery you use. The [three main methods of insulin delivery](https://diabetes.org/about-diabetes/devices-technology/insulin-pens) are _pens_ (what I use), _syringes_ (I believe they are becoming less popular), and _pumps_ (I think they're becoming more popular as technology improves).

The insulin pens are the simplest to understand, IMO. We need to learn and adjust these two different measures called the [correction factor (CF) and the carbohydrate ratio (CR)](https://www.mountsinai.on.ca/care/lscd/sweet-talk-1/what2019s-a-correction-factor-an-insulin-sensitivity-a-ratio). I inject about four times per day: one rapid-acting insulin for each meal and one slow-acting insulin for the entire day. Before I eat a meal, I need to count the carbs I think are in that meal and choose the correct amount of insulin to inject based on the CF and CR. Gluroo provides users with a table to make this calculation much simpler!

2. Are there any other data you collect in a time-series fashion, or does most of the real-world data follow the structure given here?

**Answer:** Yes! Technically, the insulin dose and the carbohydrate consumption are time-series data, but they are reported as an instance in time. The type of insulin being administered changes the absorption rate over time, so we get these plots called [insulin action curves (see Types of Insulin).](http://ddi.ucsd.edu/insulearn/terminology.html). The users of most diabetes apps will report the type of insulin they inject. So, app developers can incorporate that into the application to communicate how much **insulin on board** you currently have. The same applies to **carbohydrates on board**; pure sugar like glucose causes your blood sugar to spike much more rapidly than a carbohydrate high in fibre (that's why eating your vegetables is essential!) So, even though you consume the same amount of carbs, you can have very different glucose response curves. If we know the food being consumed, we can create better estimates of how to administer insulin.  This is called a [Glycemic Index.](https://www.diabetes.ca/resources/tools---resources/the-glycemic-index-(gi)).

3. Are there specific patterns or best practices for timing doses to optimize blood glucose control?
4. Can we build a model to perdict the blood glucose level after intaking the food that has food_glycemic_index and weights food_g?
5. What's the difference between basal and bolus insulin? Do you have a preference over using one or the other (e.g. effectiveness, side effects, etc)?
6. What's the relation between food weight in grams, glycemic index, and blood glucose levels?
7. Based on the timestamp data (bgl_date_millis), can we design a real-time alert system to warn users of impending blood glucose anomalies?
8. How do the variables like food_glycemic_index and food_g affect blood glucose levels? Can we build a model to predict these interactions?
9. How does basal insulin compare to bolus insulin in terms of managing blood glucose levels throughout the day? Is one more effective than the other for specific situations or times of day? Are there strategies behind using them together in different dosages to optimize blood sugar control?
10. Are there foods that are considered optimal based on their glycemic index and nutrient profile? Are certain foods recommended for different situations, such as managing hypoglycemia, hyperglycemia, or maintaining stable BGL during normal conditions?
11. What are some misconceptions about T1D that non-diabetics might have?
12. What are some daily challenges that you and other T1Ds face that isn't obvious to non-diabetics?
13. Besides insulin some patients may be taking other medications for their Diabetes. With this, would it be intersting for those additional information to be accounted for in visualizations? How would other medications impact daily bgl readings of patients compared to those just on Insulin?
14. Multiple readings were taken in very short timeframes with 2-5 min between readings in some cases. What type of device was used for the readings? If the readings were taken through devices such as Libre 2, is it possible to know if the readings were within the error margin of 20% to determine the accuracy of the readings?
15. Are there specific patterns or best practices for timing doses to optimize blood glucose control?
16. Can we build a model to perdict the blood glucose level after intaking the food that has food_glycemic_index and weights food_g?
17. An individual with T1D will not be able to produce insulin effectively. So while managing T1D, is there more emphasis placed on meal timings (i.e when you should eat your meals), or the post-meal insulin dosage?
18. Based on the plot, it seems as though the insulin dosage timings vary quite a lot. From my understanding, having a meal will increase BGL; this is when insulin could be dosed to reduce BGL. How are the timings of insulin dosage determined? Would this depend on the meal size (eg: thanksgiving dinner vs an average dinner)?








