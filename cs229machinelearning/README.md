## What is Machine Learning?

Two definitions of Machine Learning are offered. https://cs229.stanford.edu/notes-spring2019/lecture1_slide.pdf

Arthur Samuel described it as: "**the field of study that gives computers the ability to learn without being explicitly programmed.**" This is an older, informal definition.

Tom Mitchell provides a more modern definition: "**A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E**."

Example: playing checkers.

E = the experience of playing many games of checkers

T = the task of playing checkers.

P = the probability that the program will win the next game.

In general, any machine learning problem can be assigned to one of two broad classifications:

Supervised learning and Unsupervised learning.



## Multiple Features

We will start to talk about a new version of linear regression that's more powerful. One that works with multiple variables or with multiple features. Here's what I mean. In the original version of linear regression that we developed, we have a single feature x, the size of the house, and we wanted to use that to predict why the price of the house and this was our form of our hypothesis.

![](https://pengfeinie.github.io/images/44c68412e65e62686a96ad16f278571f.png)

But now imagine, what if we had not only the size of the house as a feature or as a variable of which to try to predict the price, but that we also knew the number of bedrooms, the number of house and the age of the home and years. It seems like this would give us a lot more information with which to predict the price.

![](https://pengfeinie.github.io/images/591785837c95bca369021efa14a8bb1c.png)

To introduce a little bit of notation, we sort of started to talk about this earlier, I'm going to use the variables X subscript 1 X subscript 2 and so on to denote my, in this case, four features and I'm going to continue to use Y to denote the variable, the output variable price that we're trying to predict. 

Let's introduce a little bit more notation. Now that we have four features, I'm going to use lowercase "n" to denote the number of features. So in this example we have n4 because we have, you know, one, two, three, four features. And "n" is different from our earlier notation where we were using "n" to denote the number of examples. So if you have 47 rows "M" is the number of rows on this table or the number of training examples. So I'm also going to use X superscript "I" to denote the input features of the "I" training example.

![image-20211206181321485](https://pengfeinie.github.io/images/image-20211206181321485.png)

As a concrete example let say X2 is going to be a vector of the features for my second training example. And so X2 here is going to be a vector 1416, 3, 2, 40 since those are my four features that I have to try to predict the price of the second house. So, in this notation, the superscript 2 here. That's an index into my training set. This is not X to the power of 2. Instead, this is, you know, an index that says look at the second row of this table. This refers to my second training example. With this notation X2 is a four dimensional vector. In fact, more generally, this is an in-dimensional feature back there. With this notation, X2 is now a vector and so, I'm going to use also Xi subscript J to denote the value of the J, of feature number J and the training example. So concretely X2 subscript 3, will refer to feature number three in the x factor which is equal to 2,right? That was a 3 over there, just fix my handwriting. So x2 subscript 3 is going to be equal to 2.

Now that we have multiple features, let's talk about what the form of our hypothesis should be. Previously this was the form of our hypothesis, where x was our single feature, but now that we have multiple features, we aren't going to use the simple representation any more. Instead, a form of the hypothesis in linear regression is going to be this, can be theta 0 plus theta 1 x1 plus theta 2 x2 plus theta 3 x3 plus theta 4 X4. And if we have N features then rather than summing up over our four features, we would have a sum over our N features.

Concretely for a particular setting of our parameters we may have H of X 80 + 0.1 X1 + 0.01x2 + 3x3 - 2x4. This would be one example of a hypothesis and you remember a hypothesis is trying to predict the price of the house in thousands of dollars, just saying that, you know, the base price of a house is maybe 80,000 plus another open 1, so that's an extra, what, hundred dollars per square feet, yeah, plus the price goes up a little bit for each additional floor that the house has. X two is the number of floors, and it goes up further for each additional bedroom the house has, because X three was the number of bedrooms, and the price goes down a little bit with each additional age of the house. With each additional year of the age of the house. Here's the form of a hypothesis rewritten on the slide. And what I'm gonna do is introduce a little bit of notation to simplify this equation. For convenience of notation, let me define x subscript 0 to be equals one. Concretely, this means that for every example i I have a feature vector X superscript I and X superscript I subscript 0 is going to be equal to 1. You can think of this as defining an additional zero feature. So whereas previously I had n features because x1, x2 through xn, I'm now defining an additional sort of zero feature vector that always takes on the value of one. So now my feature vector X becomes this N+1 dimensional vector that is zero index. So this is now a n+1 dimensional feature vector, but I'm gonna index it from 0 and I'm also going to think of my parameters as a vector. So, our parameters here, right that would be our theta zero, theta one, theta two, and so on all the way up to theta n, we're going to gather them up into a parameter vector written theta 0, theta 1, theta 2, and so on, down to theta n. This is another zero index vector. It's of index signed from zero. That is another n plus 1 dimensional vector. So, my hypothesis cannot be written theta 0x0 plus theta 1x1+ up to theta n Xn. And this equation is the same as this on top because, you know, eight zero is equal to one. Underneath and I now take this form of the hypothesis and write this as either transpose x, depending on how familiar you are with inner products of vectors if you write what theta transfers x is what theta transfer and this is theta zero, theta one, up to theta N. So this thing here is theta transpose and this is actually a N plus one by one matrix. [It should be a 1 by (n+1) matrix] It's also called a row vector and you take that and multiply it with the vector X which is X zero, X one, and so on, down to X n. And so, the inner product that is theta transpose X is just equal to this. This gives us a convenient way to write the form of the hypothesis as just the inner product between our parameter vector theta and our theta vector X. And it is this little bit of notation, this little excerpt of the notation convention that let us write this in this compact form. So that's the form of a hypthesis when we have multiple features. And, just to give this another name, this is also called multivariate linear regression. And the term multivariable that's just maybe a fancy term for saying we have multiple features, or multivariables with which to try to predict the value Y.