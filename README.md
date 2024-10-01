# Overview
Welcome to my analysis of the Gaming industary,focusing on the video game market. this project was made to understand players WANTS to improve Game sales

This data was sourced from a blog post i saw about the evolution of Gameing .which provides a foundation for my analysis, containing detailed information on Game title,	console,	genre,	publisher,	developer,	critic score,	total sales, release date and last update. Through a series of python scripts, i explore key Question.

# The Question
Here are the question i answer in my project:

1. What is the most played  Game console 

2. Which company Develop and which company Published the most games

3. What are the most played Genre

4. what are the most Sold games

5. Critic scores for the most Sold games

# Tools I Used 
- Python:  the programing language i used for my analysis

    1. Pandas Library: the python library used to analyze the Data
    
    2. Matplotib Library: the library I used to visualize my Data

    3. Seaborn Library: i used it to create advased visualize

- Jupyter Notbook: The tool i used to run my python script

# The Analysis 
Each jupyter notebook for this project aimed at investigating specific aspects of the Game market

## 1. Most played Game console
To find most played console i filtered out all the different type of game console and caculated the value count to find the Top 10 game console of all time

View my notebook: [1 Most_Used_Console.ipynb]()

### Insights
- PC is still the King.

PC platform usage is much greater than any of the other consoles. PC usage exceeds 12,000 which leaves all other platforms waist deep in its popularity.

- PS2 & DS Occupy the Second and Third Quarters.

The other platforms ranked after PC include the PlayStation 2 and the Nintendo DS probably this performance is because PC dominates the pack. Their figures look closely matching one another both in the range of 3,000-4,000.

- New Consoles (PS4 and NS) are still Relevant

Also, play a large role in the current day video gaming industry would be the PlayStation 4 and the Nintendo Switch. These consoles fall slightly within the usage rank just below PS2 and DS.

- Legacy Systems are some other currently still in use.

Even less popular replacement consoles, such as the PS and XBL still find good usage trends. This shows that older systems still have some users who appreciate them perhaps because they contain old games or other specialized categories.

- Mid Tier Services are services in the middle range.

PlayStation commercial networks and Xbox live service providers come to play in the mid tier level. This may explain their dominance in the popular online activity but not to the levels of popularity of hardware based consoles.

- Declining PS3

According to data, the PlayStation 3 (PS3) has the lowest usage trend compared to PS4 and PS2, which suggests and is expected an evolution from the older generational hardware.

Conclusion:

The statistics show some balance between the older consoles and the new ukuzisha. With the

## 2. Developers and publisher

To compare the game developers and publisher i filtered the value count .and broth it down to the to top 10 developers and publisher 

View my notebook: [2 Developers_And_Publisher.ipynb]()

### Insights
Developer Insights:

1.Unknown Developers Lead

- A large number of games in this dataset have been developed by Unknown developers, showing a lack of precise attribution for a significant portion of the data, which may represent indie developers or insufficiently documented sources.

2.Konami and Sega Prominent

- Konami and Sega stand out among known developers, with both companies contributing significantly more games than other developers. This reflects their historic and ongoing influence in the gaming market.

3.Capcom, Namco, and Square Enix's Steady Contributions

- Capcom, Namco, and Square Enix also appear as consistent contributors, though their volume is lower than Konami and Sega. These companies are known for their extensive game portfolios, including major franchises that have spanned decades.

4.Broad Spectrum of Developers

- Other developers like SNK Corporation, EA Canada, Hudson Soft, and Ubisoft appear as lower-tier contributors. These companies still have a notable impact but are dwarfed by industry giants.

Publisher Insights:

1.Unknown Publishers Lead

- Like the developers chart, a significant portion of games are listed under Unknown publishers, which may indicate independent releases or gaps in data reporting.

2.Sega and Ubisoft Dominate Known Publishers

- Among known publishers, Sega and Ubisoft are the most prominent, with Sega contributing the most games by far. This suggests these companies have not only developed but also published a large volume of titles.

3.Electronic Arts, Activision, and Nintendo’s Strong Presence

- Electronic Arts (EA), Activision, and Nintendo appear as key publishers. This aligns with their reputations as industry leaders who have published a wide variety of successful franchises.

4.Balanced Spread Among Other Major Publishers

- Companies like Sony Computer Entertainment, Microsoft, Konami, and THQ maintain a consistent presence. While their contributions are fewer than Sega or Ubisoft, they still represent key players in publishing games across multiple platforms.

Conclusion:
- The dominance of Unknown developers and publishers could point to a large portion of indie games or incomplete data attribution.

- Sega, Konami, and Ubisoft consistently rank as leading contributors to both development and publishing, reinforcing their strong presence in the gaming world.

- A handful of companies (e.g., EA, Activision, Nintendo) maintain steady positions in the middle tier for publishing, with strong historical footprints.

These insights highlight the diversity in game development and publishing, ranging from independent or less-known creators to industry giants like Sega, Konami, and Ubisoft.



## 3. Genre

Filtering top played genre. I ploted a pie chart that that showes the persentage of genre played on the used console. and from the data we know that the PC is the most played gaming system

python
```df["genre"].value_counts() .head(10)```

Misc :            9304

Action :         8557

Adventure   :    6260

Role-Playing  :  5721

Sports  :        5586

Shooter   :      5410

Platform    :    4001

Strategy    :    3685

Puzzle   :       3521

Racing    :      3425


```import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

dataset = pd.read_csv('vgchartz-2024.csv')
df = dataset

filtered_df = df[(df['console'] == 'PC') & 
                 (df['genre'].isin(['Misc', 'Action', 'Adventure', 'Role-Playing', 'Sports', 'Shooter', 'Platform', 'Strategy', 'Puzzle', 'Racing']))]

# Count the occurrences of each unique value in the filtered DataFrame
value_counts = filtered_df['genre'].value_counts() .plot(kind = "pie",autopct = "%1.1f%%", title = "Most played Genre on PC", ylabel = "" )

#print(value_counts)
```
then which gave me my Insights in a pie plot

![my](./Images/PC%20plot.png)

## 4. Most Sale
caculating the total sale of every game in every console. that was what i did to get my to get my result



## 5. Critic Scores
By puting all of the most sold games in a list. i filtered out all the game titles and added their critic scores from every console.after that using seaborn i ploted a bar chart that showes the range of the games

### Insights
- **Call of Duty Dominates** : the highest ranked game is call of Duty: Black Ops with a score above 60, followed by Call of Duty: Ghosts and Call of Duty: Advanced Warfare. this indicates a consistent trend of high scores for the franchise

- **Popular Games Across Genres**: Beyond first - person shooters, Games like Minecraft, FIFA 15, and The Elder Scrolls V: Skyrim also show high Critic scores

- **Lower Scores**: The lower end of the scale includes games like Red Dead Redemption 2 and Call of Duty: WWII, which may have received more mixed reviews