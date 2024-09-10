# Frequently Asked Questions

For now, this is a working document aggregating all of the questions we get from our trial period. We will begin merging similar questions together and organizing them into categories as we go. 

1. How do you know beforehand when to take insulin? Especially on times where you are forced to go off schedule, such as traveling on flights? Is it mostly instinct, or can you somehow predict beforehand when and how your BGL will fluctuate?

> **Answer:** Great question! There's not much instinct at all! There are a few similar ways of doing this that depend on the method of insulin delivery you use. The [three main methods of insulin delivery](https://diabetes.org/about-diabetes/devices-technology/insulin-pens) are _pens_ (what I use), _syringes_ (I believe they are becoming less popular), and _pumps_ (I think they're becoming more popular as technology improves).

> The insulin pens are the simplest to understand, IMO. We need to learn and adjust these two different measures called the [correction factor (CF) and the carbohydrate ratio (CR)](https://www.mountsinai.on.ca/care/lscd/sweet-talk-1/what2019s-a-correction-factor-an-insulin-sensitivity-a-ratio). I inject about four times per day: one rapid-acting insulin for each meal and one slow-acting insulin for the entire day. Before I eat a meal, I need to count the carbs I think are in that meal and choose the correct amount of insulin to inject based on the CF and CR. Gluroo provides users with a table to make this calculation much simpler!

2. Are there any other data you collect in a time-series fashion, or does most of the real-world data follow the structure given here?

> **Answer:** Yes! Technically, the insulin dose and the carbohydrate consumption are time-series data, but they are reported as an instance in time. The type of insulin being administered changes the absorption rate over time, so we get these plots called [insulin action curves (see Types of Insulin).](http://ddi.ucsd.edu/insulearn/terminology.html). The users of most diabetes apps will report the type of insulin they inject. So, app developers can incorporate that into the application to communicate how much **insulin on board** you currently have. The same applies to **carbohydrates on board**; pure sugar like glucose causes your blood sugar to spike much more rapidly than a carbohydrate high in fibre (that's why eating your vegetables is essential!) So, even though you consume the same amount of carbs, you can have very different glucose response curves. If we know the food being consumed, we can create better estimates of how to administer insulin.  This is called a [Glycemic Index.](https://www.diabetes.ca/resources/tools---resources/the-glycemic-index-(gi)).

3. Are there specific patterns or best practices for timing doses to optimize blood glucose control?

> **Answer:** This is a tricky question because it depends on what you try to optimize for. For engineers and scientists, we think very quantitatively and want to min/max and hyperoptimize everything! But, imagine living your life where multiple times a day, if you make a mistake, you risk death (it's a very low risk with today's technology but accidents can still happen). Even if you do everything right, sometimes your body just reacts differently and in an unpredictable way, you can experience hypoglycemia when you're sleeping! 

> For every meal of every day for the rest of your life, you need to count how many carbs you will consume and predict the right amount of insulin. There are no vacations from this. It adds at least 10 hours per week of extra work that healthy individuals don't have to deal with. This why much of the focus for diabetes management research has turned to alleviating [diabetes distress.](https://professional.diabetes.org/sites/default/files/media/ada_mental_health_workbook_chapter_3.pdf) So a significant part of what our goal is here with this project, is to develop ways to make this optimization as painless as possible. We're trying to ease the cognitive burden of diabetes so they can optimize their insulin timings without much cognitive burden. 

> Now, with that being said, if we just treated PWDs like emotionless robots, yes, there would be optimal timing of doses and meals. So, for a Multiple Daily Injection (MDI) diabetic like myself, the more routine you can be with your life, the more similar your meals are to one another, and the easier it gets. This is because I need to take, on average, four injections per day, more if I make a mistake and don't take enough insulin. I need to take one basal insulin injection (the baseline) in the morning (the timing is up to the individual; the insulin is slow-acting and lasts for 36 hours) and three bolus injections (one for each meal of the day). Learning the optimal time to take your bolus injection depends on your experience with the meal, you need to learn the correct amount of insulin, and the proper timing of insulin. The correct timing is usually anywhere from 30 minutes before eating to 15 minutes after you start eating.

4. Can we build a model to perdict the blood glucose level after intaking the food that has food_glycemic_index and weights food_g?

> **Answer:** Yes, we can! That will likely be a significant part of our work that gets incorporated into multiple aspects of our project. 


5. What's the difference between basal and bolus insulin? Do you have a preference over using one or the other (e.g. effectiveness, side effects, etc)? 

6. How does basal insulin compare to bolus insulin in terms of managing blood glucose levels throughout the day? Is one more effective than the other for specific situations or times of day? Are there strategies behind using them together in different dosages to optimize blood sugar control?

> **Answer:** 
> *  **Basal insulin** is your baseline. Healthy pancreas secrete a small amount of insulin into their bodies to keep sugar levels stable. You take this everyday around the same time, and except for special circumstances, its generally always the same amount but there are adjustments we make to this dose because our bodies and lifestyles change slowly over time.

>* **Bolus Insulin** is your rapid-acting insulin. This starts working within 10 minutes and peaks around 40 minutes, it's completely gone after five hours, but its effects for most are fairly negligible after 2-3 hours. We take this for when we eat because we get a massive spike in blood sugar if we don't. [Our blood is only supposed to have ~4g of glucose in it at any given time.](https://journals.physiology.org/doi/full/10.1152/ajpendo.90563.2008) Now look at the back of a can of any soft drink, Cokes have about 45g of sugar! Every time you consume something that exceeds the ability of your baseline insulin to absorb, you need to bolus. 

> So there is no preference; you need both, and they do different things; they complement each other. Basal insulin makes bolus insulin more predictable and easier to manage.

6. What's the relation between food weight in grams, glycemic index, and blood glucose levels? 

7. How do the variables like food_glycemic_index and food_g affect blood glucose levels? Can we build a model to predict these interactions?

> **Answer** The more grams of carbs consumed, the higher it will cause your blood glucose to spike, so the more insulin you need. The Glycemic Index is how rapidly it causes your blood sugar to spike. Essentially, all carbohydrates will eventually be turned into sugar in your body if you can digest them, but the speed at which you can digest them varies pretty dramatically. Generally, the closer a carbohydrate is to pure sugar, the faster your body can absorb it and the higher its index will be. The more fibre a carbohydrate has, the longer it will take to digest. The closer to 0 a Glycemic Index is, the slower the glucose spike will be.

7. Based on the timestamp data (bgl_date_millis), can we design a real-time alert system to warn users of impending blood glucose anomalies?

> **Answer** This may be a valuable exercise to familiarize yourself with the data, but these systems already exist in all continuous glucose monitoring apps. The original main purpose of CGMs was to prevent and notify T1Ds of high or low blood glucose. The technology has had a profound impact on the quality of life of T1Ds, second only to the discovery of insulin itself. I don't know if they track the numbers on this, but I would confidently say that CGMs have saved many T1Ds from early accidental death.

10. Are there foods that are considered optimal based on their glycemic index and nutrient profile? Are certain foods recommended for different situations, such as managing hypoglycemia, hyperglycemia, or maintaining stable BGL during normal conditions?

11. What are some misconceptions about T1D that non-diabetics might have?

> **Answer:** It's becoming less common, but people seem to think that T1D is caused by eating too much sugar. T1D is an autoimmune disorder. Autoimmune disorders tend to run in families, but they present differently, so it's partly a genetic problem where the individual's immune system is too easily triggered into attacking something in its own body rather than the invaders it is supposed to attack. I have family members with [Graves Disease](https://www.mountsinai.org/health-library/diseases-conditions/graves-disease), [Hashimoto's Disease](https://www.mayoclinic.org/diseases-conditions/hashimotos-disease/symptoms-causes/syc-20351855), and [Rheumatoid Arthritis](https://www.mayoclinic.org/diseases-conditions/rheumatoid-arthritis/symptoms-causes/syc-20353648), and [Lupus](https://www.mayoclinic.org/diseases-conditions/lupus/symptoms-causes/syc-20365789). 

> **Answer:** There are many other misconceptions like "Why don't you just stop eating carbs?" Which is generally a bad and dangerous thing for T1Ds to do because it greatly increases the chances of [Diabetic Ketoacidosis](https://www.mayoclinic.org/diseases-conditions/diabetic-ketoacidosis/symptoms-causes/syc-20371551). 

12. What are some daily challenges that you and other T1Ds face that isn't obvious to non-diabetics?

> **Answer** It's annoying to have to carry insulin around with me everywhere. If I forget it in my car, the insulin will probably be ruined from being too hot or cold! There are probably many more that we can add to this list later.

13. Besides insulin, some patients may be taking other medications for their Diabetes. With this, would it be intersting for those additional information to be accounted for in visualizations? How would other medications impact daily bgl readings of patients compared to those just on Insulin?

> **Answer**: Many many factors impact insulin, read: [42 Factors That Affect Blood Glucose?! A Surprising Update](https://diatribe.org/diabetes-management/42-factors-affect-blood-glucose-surprising-update) However, this project will only focus on the **major** factors that affect blood glucose. These other things amount to 5% of the signal in the noise. Once we build strong enough models and are confident we have hit a plateau, we can start looking at ways to incorporate other information to improve our models, but that requires asking more work from diabetics in their tracking, and for most the tradeoff probably isn't there for the added value they might get. 

14. Multiple readings were taken in very short timeframes with 2-5 min between readings in some cases. What type of device was used for the readings? If the readings were taken through devices such as Libre 2, is it possible to know if the readings were within the error margin of 20% to determine the accuracy of the readings?

> **Answer**:

15. Are there specific patterns or best practices for timing doses to optimize blood glucose control?

> **Answer**:


16. Can we build a model to perdict the blood glucose level after intaking the food that has food_glycemic_index and weights food_g?

> **Answer**:


17. An individual with T1D will not be able to produce insulin effectively. So while managing T1D, is there more emphasis placed on meal timings (i.e when you should eat your meals), or the post-meal insulin dosage?

> **Answer**:


18. Based on the plot, it seems as though the insulin dosage timings vary quite a lot. From my understanding, having a meal will increase BGL; this is when insulin could be dosed to reduce BGL. How are the timings of insulin dosage determined? Would this depend on the meal size (eg: thanksgiving dinner vs an average dinner)?

> **Answer**:






