{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Sarcasm Classification with Subreddits\n",
    "\n",
    "---\n",
    "\n",
    "## Problem Statement\n",
    "\n",
    "Sarcasm is difficult to grasp for non-native english speakers, let alone for machines. The lack of body language and verbal cues in computer-mediated communication, makes it especially hard to detect tone, intent, and word meaning. Although machine learning has come a long way, scientists are constantly looking for new ways to push the accuracy of existing models. Additionally, the high cost of labeling data spurs anyone remotely interested in building an effective model to search for alternative solutions.\n",
    "\n",
    "In this analysis, we will comparing various classification models, utilizing Naive Bayes, Logistic Regression, and other techniques to push for accuracy in the classification of two subreddits: *askscience* and *shittyaskscience*. *Askscience* is an open platform that answers scientific queries, while *shittyaskscience* is a humourous version of it mostly laced with irony. We will be using reddit's API to obtain the data for this analysis.\n",
    "\n",
    "The main metric we will be focusing on in this analysis will be accuracy as we are trying to obtain a good amount of data with the least amount of type I and type II errors. This analysis will primarily benefit companies selling science related products, and online forum moderators looking to automate their work. We will deem this analysis successful if we are able to construct a classification model that can predict a subreddit based on text with an accuracy above 80%.\n",
    "\n",
    "---\n",
    "\n",
    "## Contents\n",
    "\n",
    "1. [Data Collection](#1.-Data-Collection)\n",
    "2. [Data Cleaning](#2.-Data-Cleaning)\n",
    "    * 2.1 [First Look: Head, Shape](#2.1-First-Look:-Head,-Shape)\n",
    "    * 2.2 [Second Take: Head, Shape, Null](#2.2-Second-Take:-Head,-Shape,-Null)\n",
    "    * 2.3 [Data Cleaning](#2.3-Data-Cleaning)\n",
    "3. [EDA](#3.-EDA)\n",
    "    * 3.1 [Number of Posts by Month](#3.1-Number-of-Posts-by-Month)\n",
    "    * 3.2 [Word Occurrences](#3.2-Word-Occurrences)\n",
    "        * 3.2.1 [Word Cloud](#3.2.1-Word-Cloud)\n",
    "        * 3.2.2 [High Count Words](#3.2.2-High-Count-Words)\n",
    "        * 3.2.3 [Common Words](#3.2.3-Common-Words)\n",
    "4. [Modeling](#4.-Modeling)\n",
    "    * 4.1 [Baseline Model](#4.1-Baseline-Model)\n",
    "    * 4.2 [Spacy Verbs, Nouns, Proper Nouns](#4.2-Spacy-Verbs,-Nouns,-Proper-Nouns)\n",
    "    * 4.3 [Model Selection](#4.3-Model-Selection)\n",
    "        * 4.3.1 [Gridsearch Count Vectorizer + Logistic Regression](#4.3.1-Gridsearch-Count-Vectorizer-+-Logistic-Regression)\n",
    "        * 4.3.2 [Gridsearch Count Vectorizer + Naive Bayes](#4.3.2-Gridsearch-Count-Vectorizer-+-Naive-Bayes)\n",
    "        * 4.3.3 [Gridsearch TfidfVectorizer + Logistic Regression](#4.3.3-Gridsearch-TfidfVectorizer-+-Logistic-Regression)\n",
    "        * 4.3.4 [Gridsearch TfidfVectorizer + Naive Bayes](#4.3.4-Gridsearch-TfidfVectorizer-+-Naive-Bayes)\n",
    "        * 4.3.5 [Comparison of Metrics](#4.3.5-Comparison-of-Metrics)\n",
    "    * 4.4 [Final Model](#4.4-Final-Model)\n",
    "5. [Conclusions and Recommendations](#5.-Conclusions-and-Recommendations)\n",
    "\n",
    "---\n",
    "\n",
    "## 5. Conclusions and Recommendations\n",
    "\n",
    "We recommend that companies selling science related products utilize our method to weed out product reviews that are classified as positive, and look through them to see if they are 'sarcastic'. This would theoretically reduce the number of posts they would have to review by over 80%. We also recommend that they take note of posts with words pertaining to: cannibals, fish, cats, chickens, backwards, bears, and horses, as they are likely to be sarcastic.\n",
    "\n",
    "There are limitations with regards to this analysis. Most notably, that it may not be directly translatable to any use-case. As 'shittyaskscience' posts are written with the intent of humour, it may not be the case with product review. For example, a customer may have a more harsh tonality with regards to their sarcasm and it is unclear if our model would be able to detect that. Also, we are unable to determine the accuracy at which it can classify outside of 'science' related posts.\n",
    "\n",
    "This analysis could be further improved in the following ways:\n",
    "* Finding alternative datasets to test the classification\n",
    "* Utilizing ensemble models to push the accuracy of the model\n",
    "\n",
    "In conclusion, we did manage to achieve an accuracy score of 81% which surpasses our original goal of 80% accuracy. This was achieved utilizing count vectorization and logistic regression. "
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}
