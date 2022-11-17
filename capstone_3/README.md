## Water sensor data capstone

The dataset comes from Kaggle. What is Kaggle? Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.  
 - https://www.kaggle.com/datasets/nphantawee/pump-sensor-data
 
 This dataset was posted by someone trying to figure out if there was a way to predict when water pumps would fail for getting clean water to his town.  Here is his context "I have a friend who working in a small team that taking care of water pump of a small area far from big town, there are 7 system failure in last year. Those failure cause huge problem to many people and also lead to some serious living problem of some family. The team can't see any pattern in the data when the system goes down, so they are not sure where to put more attention."  From what we see, the water pumps are pretty crucial to the towns well being, so it would be great to be able to predict and anticipate a water pump failure.
 
 ### Data Cleaning and EDA:
 
 The data in this set is fairly clean.  There are about 52 sensors, all with numerical data.  55 columns and ~220,000 rows.  The first thing to do is take a glimpse at the data and check out how each of the sensors operate.  The linegraph of each sensor tells us that there are many sensors that do the same thing, or measure the same thing.  So we want to use sensors that have different graphs, so that way we can get the best results from our model.
 
 The 2 variable I chose were to have the machines either 'working' or 'not working'.  There were 7 instances in the data where the sensors failed. After those 7 instances there were 'recovery' periods for the sensors.  I chose to combine the recovering and failed status in the same variable 'failed', so now I have 2 variables.
 
 After that I looked at the correlation on all of the sensors to figure out what sensors I should use for my model data. I landed on 13 sensors, and a column called operational.  The operational column was set to tell me either a 1 for 'working' status, and 0 for 'not working' status. Even in my selected group I had some sensors that had similar graphs, so I removed one from the model data. The final step in getting the data ready for the model was to remove na's from the set, this decreased the total lines of data down to 219,933, still plenty of data for our model.
 
 ### Histograms and box plots:
 
 The next step in the process was taking a look at each sensors histogram and box plot to get a sense of how each sensor operated and where the efficent operating levels were.
 
 Viewing all of the sensors in histograms and box plots also gave a good sense that each sensor in my data set was very different and had very different measurements - this is a good sign that the model will have good success and avoid overfitting on similar sensors.
 
 ### Modeling:
 
 The data proved to be very good for modeling.  The data ended up being very accurate, and also had little loss. From the graphs, I attempt to show how quickly the model gains accuracy, and how quickly it diminishes loss.  This was the case even with adding more layers and changing the batch sizes.
 For the model, I'll suggest using the first model named model. The other models, model1, and model2 aren't as accurate as model, and looking at the graphs, it seems model does a great job of decreasing loss and maximizing accuracy.
 
 ### Additional thoughts on the project and next steps:
 In analyzing and creating a model(s) for this project, it raised a few questions for me.  While the model was excellent at minimizing loss and maximizing accuracy, it wouldn't spit out numbers/frequencies that give a sense of when the instruments/sensors would fail.
 For this, I think looking at implementing a K-Means clustering analysis with 2 clusters would help provide some more color on the sensors.  This would be more helpful for someone who is involved with these sensors and who depends on them to know if and when they can expect a failure in the water sensors.  By clustring the data, I should be able to see or have a good idea of what values the sensors can fail at.  The hope is that the clustering shows a distinct difference between what would be a normal working operation, and a smaller clustered not working or failed level.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 