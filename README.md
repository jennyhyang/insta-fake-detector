# Instagram Fake User Detector

Collaborators: Idris Wardere


Credit to Kristo Radion Purba for the dataset. Check out his paper:

K. R. Purba, D. Asirvatham and R. K. Murugesan,
"Classification of instagram fake users using supervised machine learning algorithms,"
International Journal of Electrical and Computer Engineering (IJECE),
vol. 10, no. 3, pp. 2763-2772, 2020.

# The Data

The dataset includes information on 17 different features of 65326 Instagram users. Using
these features, we aimed to predict whether a user was fake or not. Among these 17 features,
we selected 13 of which to build our models on. These 13 features included the number of posts
a given user had, the number of followers, the number of following, their biography length, 
their profile picture availability, their link availability, their average caption length, their
non-image media (video and carousel) percentage, their engagement rate in likes (total likes divided by
number of media and number of followers), their engagement rate in comments (total comments divided
by number of media and number of followers), their location tag percentage, their average hastag count,
and their average interval between posts. We chose to include these features in our models because
they are easily collected information.

# Processing the Data

We began by counting the number of NAs within the dataset. There were none. Then we created 
variables which separated the features we had selected from the rest of the data. Since the
variable we aimed to predict was categorical ('f' for fake or 'r' for real), we defined a function
which transformed these labels into numbers (1 for fake and 0 for real). After that, we separated
the data again into training and validation datasets.

# Training the Models

Before training our models, we defined a function that calculated the error rate based on any
model's predictions. Then we trained the following models: a Random Forest Classifier, a Logistic
Regressor, a KNeighbors Classifier, an Ada Boost Classifier, and a Linear Regressor. We tweaked the
hyperparameters on our models to optimize the validation error. Then we calculated the error rate on 
the validation and training datasets for each model.

# Conclusion

We discovered that the **Random Forest Classifier** performed best with a validation error of 10.9%.
The model had the following hyperparameters: 

`n_estimators = 100`

`max_depth = 10`

`random_state = 0`

Since the validation error was similar to the train error (9.7%), we believe the model generalizes well.
Lastly, we examined the feature importances of the Random Forest Classifier and found that the most
important feature was link availability while the least important feature was profile picture availability.
