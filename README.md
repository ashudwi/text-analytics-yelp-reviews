# text-analytics-yelp-reviews

### Introduction

This data consisting of YELP reviews has 5366 reviews from Nov 2005 to Nov 2018 from 5161 unique users. The reviews are for the buffet served at 2 restaurants located in Vegas namely - The Bellagio and The MGM Grand. The data is granular at the review level. For each review we have attribute such as the userID (a unique identifier given to every user), timestamp of the review down to the hour, votes to the review if it was funny,helpful,etc and a rating(star) that a user gives to rate the restaurant buffet. There are instances where the same user has given multiple reviews over the years. After removal of records prior to 2015, we are left with 2345 reviews from 2283 unique users from 2015 to Nov 2018 upon which we perform all our analysis.

### Frequency Analysis

I performed a Frequency Analysis over the data treating words as unigrams (word as is) as well as on bi-gram representation of words. On evaluating the results from the unigram frequency analysis, I could make certain observations such as words like “food”,“eat”,“vegas” have a low tf-idf score as they probably appear in a lot of reviews understandeably. On visualising the wordcloud with the highest tfidf values, words with the highest tf-idf values seem to be words that convey a strong sentiment or feeling such as “amazing” or “savage” or “inappropriate”. I think that these tf-idf scores could be used to potentially gain insights into what aspects of a buffet are popular or unpopular with customers when it comes to reviewing after filtering for adjectives or the data could be used with bigrams to see what words (adjectives) are generally used to describe those aspects (positive or negative connotation). I ran a tf-idf over a bigram representation and saw that the top 30 odd bigram phrases have the same tf-idf score. The phrases that turn up in the wordcloud with the highest tf-idf scores are for example - “elegant presentation”,“overly priced”,“outrageous prices”, “beauful deserts”,“waiting line”,etc. These phrases give meaningful insights such as people tend to talk about tasty deserts and annoying waiting lines in ther review. Pricing is a recurring theme in the reviews that seems to bother people enough to write about in their reviews. While the unigram tf-idf was hepful, I felt that the bigram tf-idf or the bigram frequency analysis gave more context to the results making the insights more meaningful

### Sentiment Analysis (Lexicon based)

For the sentiment analysis, I chose to analyze sentiment using the lexicons - SenticNet and slangSD. While researching upon the various lexicons available for sentiment analysis, I read that the framework for SenticNet is designed to focus on sentence structure and it maintains the semantic-preservation representation of natural language concepts. It is also often used for big social data analysis especially for trend discovery and social media marketing. Keeping these points in mind,I thought that this lexicon could be of value here considering the source of these YELP reviews. I chose slangSD as the other lexicon to analyze as slangSD was built primarily with the goal to analyze online user-generated content that is usually short and informal. It is built upon a dictionary of slang words to aid sentiment analysis of social media content.Through the frequency analysis,I did come across words that seemed like slangs and hence I thought that it this lexicon could potentially be usefulin this case. I do think that if i had more additional information in the data such as the age of users, I would have more confidence in deciding whether to choose this lexicon or not considering that slangs are generally used by a younger population.
I analysed and looked at  -
*sentiment comparison by lexicon on a daily basis
*sentiment comparison by lexicon per review



### Additional Analysis

Comparison of rating vs sentiment by looking at the distribution spread
Extracting words that to calculate sentiment scores and evaluating the word list to explain differences in sentiment scores across lexicons

### Takeaways 

The yearly avg sentiment for both the restaurants is roughly the same. It’s slightly higher for The Bellagio though it remains below 0.25 for both. By visualising this sentiment evolve through the years, it’s interesting to see that for Bellagio the sentiment has progressively gone down over the years while for MGM it went up in 2017 after declining in 2016, and again has gone down in 2018. By looking at the daily avg sentiment of reviews only for “brunch”, it’s tough to point out a specific trend or a pattern that helps distinguish between both the restaurants becuse of the spikes, but we do see that on certain days the sentiment goes beyond +1. On smoothening the data/spike in the data, we can observe that there is more variation in the scores for MGM. We also observe that in the earlier half of 2018, MGM had a lower daily avg sentiment but in the second half we can see it increase significantly relative to the Bellagio.
