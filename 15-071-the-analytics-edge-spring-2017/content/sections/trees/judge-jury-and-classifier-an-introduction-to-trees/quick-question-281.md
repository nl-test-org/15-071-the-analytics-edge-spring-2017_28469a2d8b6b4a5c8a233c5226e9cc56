---
course_id: 15-071-the-analytics-edge-spring-2017
layout: course_section
parent_title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
title: '4.2 Judge, Jury, and Classifier: An Introduction to Trees '
type: course
uid: 8f336b6d3260d3a128f288e99dda1c42

---

*   [<Video 4: CART in R]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [4.2.1Video 1: The Supreme Court]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees)
*   [4.2.2Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-253)
*   [4.2.3Video 2: CART]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-2-cart)
*   [4.2.4Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-258)
*   [4.2.5Video 3: Splitting and Predictions]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-3-splitting-and-predictions)
*   [4.2.6Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-267)
*   [4.2.7Video 4: CART in R]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [4.2.8Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-281)
*   [4.2.9Video 5: Random Forests]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)
*   [4.2.10Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-297)
*   [4.2.11Video 6: Cross-Validation]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-6-cross-validation)
*   [4.2.12Quick Question]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/quick-question-306)
*   [4.2.13Video 7: The Model v. The Experts]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-7-the-model-v-the-experts)
*   [\>Video 5: Random Forests]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)

Quick Question
--------------

Compute the AUC of the CART model from the previous video, using the following command in your R console:

as.numeric(performance(pred, "auc")@y.values)

What is the AUC?

Exercise 1

&nbsp;Numerical Response&nbsp;

Explanation

If you run the command given above after going through the commands in Video 4, you get an AUC of 0.6927.

Now, recall that in Video 4, our tree had 7 splits. Let's see how this changes if we change the value of minbucket.

First build a CART model that is similar to the one we built in Video 4, except change the minbucket parameter to 5. Plot the tree.

How many splits does the tree have?

Exercise 2

&nbsp;Numerical Response&nbsp;

Explanation

You can build a CART model with minbucket=5 by using the following command:

StevensTree = rpart(Reverse ~ Circuit + Issue + Petitioner + Respondent + LowerCourt + Unconst, method="class", data = Train, minbucket=5)

If you plot the tree with prp(StevensTree), you can see that the tree has 16 splits! This tree is probably overfit to the training data, and is not as interpretable.

Now build a CART model that is similar to the one we built in Video 4, except change the minbucket parameter to 100. Plot the tree.

How many splits does the tree have?

Exercise 3

&nbsp;Numerical Response&nbsp;

Explanation

You can build a CART model with minbucket=100 by using the following command:

StevensTree = rpart(Reverse ~ Circuit + Issue + Petitioner + Respondent + LowerCourt + Unconst, method="class", data = Train, minbucket=100)

If you plot the tree with prp(StevensTree), you can see that the tree only has one split! This tree is probably not fit well enough to the training data.

CheckShow Answer

*   [BackVideo 4: CART in R]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-4-cart-in-r)
*   [ContinueVideo 5: Random Forests]({{< baseurl >}}/sections/trees/judge-jury-and-classifier-an-introduction-to-trees/video-5-random-forests)