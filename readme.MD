# link (click link, then cntr + F9 on loaded page)
https://colab.research.google.com/github/leexa90/FoodClub_helper/blob/master/FoodClub_Bets.ipynb

This is high risk, high reward style meant to increase long term profit. Expected long term profit is 1.95, which is about 15% higher than typical other players like boochi_target(1.83). Expected means long-term behaviour

# Technical details, skip if you dont wanna know
I used 9.5 years of food club data to fit a linear logistic regression model to predict winning probabilities that takes into account the pirate and opening odds. In technical terms, each pirates had their own intercept and the opening odds for each priate was calculated as {1/(opening odds)} / Sum_across_arena {1/(opening odds)}  The expected winnings was calculated on current odds * predicted_winning_rate. I used all 3125 combinations of bets to pick up bets that give the best returns. However, as a risk aversion measure, i limited the maximum odds to ~80 concretely explained as the following procedure (found to reduce variance in winnings with no loss of performance).

a. identify top 10 bets with: i. odds < 80, ii. expected winnings > 1.03

b. identify more bets with : i. odds  < 80, ii. expected winnings within 0.05 of those in (a)

c. chose the top 10 (or less) bets with the lowest odds. 

# Findings based on my model
i. food adjustments do not affect my model, they are probably factored into winning rate

ii. opening odds are better predictors of winning probabilities then closing odds. 

iii. if the odds of a pirate has dramatically increased, it is very likely that this pirate gives a high expected return. You should thus take account of closing odds when you bet
