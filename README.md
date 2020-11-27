**1. Title:** It's beginning to look a lot like #Christmas

**2. Abstract:**
  *A 150 word description of the project idea, goals, datasets used. What's the motivation behind your project? How do you propose to extend the analysis from the paper? What story would you like to tell, and why?*

It is a well-known marketing belief that users are more active on social media during major holidays (e.g. Christmas, New Year), and advertisements are carefully planned to target these special days. Following the replication strategy of the paper, we attempt to replicate the statement that people tweet more on holidays. To do so, we use the paper's EgoTimelines dataset, that we augment with information on origin countries collected with the Twitter API, and corresponding national and international holidays. We want to confirm or infirm this belief, and identify recurrent patterns among different countries.


**3. Research Questions:**
  *A list of research questions you would like to address during the project.*

  - Do users tweet more during holidays?
  - Do users from different countries tweet more during their specific holidays?
  - Are there any meaningful patterns that could indicate a correlation between a nation's activity on Twitter and its holidays?

**4. Proposed dataset:**
  *List the dataset(s) you want to use, and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you've read the docs and some   examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible given the datasets at hand.*

  The proposed dataset is EgoTimelines which contains 17244 unique egoIDs. There is already a lot of material to answer the first question: since each row in this dataset describes a tweet, we know each of these egos posted at least once.
  
  To analyze the last two questions we need to obtain the country of each user and we'll do this by calling the Twitter API on each egoID, then extract the location from the response, then use a Place API that will give us the country code of the location.
  
  Afterwards, we need to retrieve the national holidays of each country, or of a selection of countries. There are two options that we could use: either use an API, or an already existing database (e.g. scraping from Wikipedia). However, we expect to face significant challenges to get a good quality sample. Some users can't be found anymore, some were suspended and more than half of the total have a null location. That leaves us with nearly a quarter of the whole data from which some locations will not be distinguished by the Place API. We can estimate that we'll have about 3000 users to work with.

**5. Methods:**


  1) Data collection and preprocessing: we will extend the EgoTimelines dataset with  origin countries, and map the dates in the dataset with national holidays.

  2) Analysis of general activity during holidays: we will choose a number of common holidays (e.g. Christmas, Easter, Ramadan) and analyze the twitter activity (number of tweets posted) by matching the timestamps of the tweets with these dates, and creating plots to visualize patterns.

  3) Analysis of activity by country: we will preprocess the data by grouping users by countries, and remove those who don't have a valid location. We repeat the analysis of 2).

  4) Identification of correlation between Twitter activity and holidays: we apply reverse engineering to check if other spikes in activity can be matched to the presence of a holiday. We will back this assumption with statistical analyses.

**6. Proposed timeline*:**

  - Step 1 (data collection and preprocessing) -- Deadline 3/12 
  - Step 2 (Analysis of general activity during holidays) -- Deadline 6/12 
  - Step 3 (Analysis of activity by country) -- Deadline 11/12 
  - Step 4 (Correlation between Twitter activity and holidays) -- Deadline 16/12 
  - Preparation of deliverables -- Deadline 18/12 
      * Report/datastory
      * Video
      * Clean final code

**7. Organization within the team:**
  *A list of internal milestones up until project milestone P4. Add here a sketch of your planning for the next project milestone.*

  - Step 1 (data collection and preprocessing) -- Adina
  - Step 2 (Analysis of general activity during holidays) -- Janody + Marcus
  - Step 3 (Analysis of activity by country) -- Marcus + Adina
  - Step 4 (Correlation between Twitter activity and holidays) -- Janody
  - Preparation of deliverables -- All


**8. Questions for TAs (optional):**
  Add here any questions you have for us related to the proposed project.
