# Module20_CapstoneP1

This is a short summary of the work involved in this project. There are 6 parts to the Jupyter Notebook.

•	Business understanding
•	Data understanding
•	Data preparation
•	Modeling
•	Evaluation
•	Deployment

There are a total of 5 files in this repository (1 readme.md; 1 jupyter notebook – Capstone_v02.ipynb in the main folder and 3 images in the images folder)
The notebook can be found at: 

https://github.com/sinclaireric77/Module20_CapstoneP1/blob/main/Capstone_v02.ipynb

1st part – Business understanding
As an avid golfer and a 4 handicap, I understand the value of working on every part of the game. However, too many people focus only on specifics like hitting the ball as far as possible and neglect other parts of their training. Hiring a specialized coach is expensive, where do we put the efforts to have the biggest return? What aspect of the game should we work on first?
In this module, we will look at the stats from the PGA tour and try to answer the following questions:
a) Are there categories or aspects of the game that are more important than others?
b) What features or qualities a golfer should focus on and train to make it to the next level?

2nd part – Data understanding
The data comes from the PGA tour and is available for everyone to download at: https://www.pgatour.com/stats
There are tons of categories and data for the years from 2008 to 2024. Some categories have data older than that, but the target goes back to 2008 only. That's when the PGA tour initiated the tour championship where the 30 best players face off in a championship event. This is going to be our target.
Based on all the features, did a player make it to the tour championship?
On top of the target, we will use the following features to build our dataset:
•	Tee to green stats, which includes strokes gained off the tee, strokes gained on approach and strokes gained around the green
•	Putting stats
•	Driving stats, which include distance, accuracy, smash factor, rough tendency, percentage of yardage covered, spin rate, apex, distance from the edge of fairway, clubhead speed, carry distance and carry efficiency
•	Approach to green stats, which include green in regulation, GIR under 75 yards, GIR over 200 yards, GIR from the bunker, GIR from other areas, Going for it, proximity to the hole, proximity from under 100 yard, proximity from over 275 yards and proximity from the rough.
•	Scrambling stats

3rd part – Data Preparation
The trickiest part here was to upload all the data to a single file at the time. Because the PGA tour stats are online and downloadable by year, it had to be done manually for each statistic
-	Uploaded all data, file by file – one per year and per statistic
-	Added all the stats together
-	Created 2 functions to convert feet and inches in decimal and string with percentage to numbers
-	Converted everything to numeric
-	Merge all years together

4th part – Modeling 
In this section, I looked at different 4 models each (Logistic Regression, Decision Tree, KNN and Support Vector Machine):
-	Created a pipeline with StandardScaler() and GridSearch for each of them

Results
Logistic Regression, score of 91.2% with liblinear, l1 and C=0.5
Decision Tree, score of 86.1% with gini and max_depth = 4
KNN, score of 89.0% with distance and n_neighbors=12
SVM, score of 91.8% with linear and degree=2
The best model ended up being the Support Vector Machine. Note also that all models ran roughly the same amount of time for total processing.

5th part – Evaluation
It seems like our Support Vector model gives us the best results with an accuracy of 91.8%, which is very acceptable in our case. This would mean it would have predicted close to 28 players out of 30 every year to make it to the tour championship.
The top 6 features are:
•	1- Strokes gained off the tee
•	2- Strokes gained on approach
•	3- Putting
•	4- Strokes gained around the green
•	5- Avoiding the rough
•	6- Carry Efficiency
 

5th part – Deployment
So what does this mean in real terms?
It looks like “strokes gained off the tee” is the most important features, but looking at other stats the distance (dd_rank) is not as important as avoiding the rough (dr_rough_p) and being efficient at keeping the ball in the fairway (dr_carry_eff). That means a golfer should focus more on accuracy off the tee versus trying to get more distance. This reflects really well for 2024 where the most successful golfer Scottie Scheffler is not the longest off the tee, but he's one of the most accurate.
Next, we can also see that putting is a really important factor and that proximity to the hole is not (proxi_hole). That means that a great putter can compensate for lacunes in their long game (iron play). This is interesting because personally this is new to me. I always practiced my iron play a lot more for accuracy compared to putting. Putting is no fun to practice but I guess it should be a bigger focus for trainers.
