# Flip Charts

[Flip Charts](https://www.lukaswadya.com/flipcharts/index.html) is a project that aims to help us better understand voting trends in US presidential elections by visualizing how often states flip between parties. This project was inspired by [270 To Win's](https://www.270towin.com/) excellent interactive maps tracking party wins at the state and national levels over time. In order to gain a better understanding of changes in political polarization throughout US history, I wanted to create similar visualizations that focused on vote flips between elections instead of party wins.

To build these dashboards, I started by collecting data on [presidential election winners](https://en.wikipedia.org/wiki/List_of_United_States_presidential_elections_by_popular_vote_margin) and [election results by state](https://en.wikipedia.org/wiki/List_of_United_States_presidential_election_results_by_state) from Wikipedia, which I used because it already had the data I needed in a tabular format. I then used [Gregor Weichbrodt's handy conversion tool](https://wikitable2csv.ggor.de/) to write the Wikipedia tables to CSV files. Next I used Python and Jupyter Lab to assemble a clean data set from the raw CSV data. All code, data, and html files are saved to this GitHub repository. Finally, I created all visualizations in Tableau Public, which also hosts the [source file for the dashboards](https://public.tableau.com/profile/lukas.wadya#!/vizhome/USPresidentialElectionStateFlips/Intro).

# Repository File Hierarchy

* **code** - Jupyter notebooks files used to clean data and prepare it for use in Tableau
  * **flip_data_merge.ipynb** - creates final Tableau data source by merging pres_wins_by_election.csv and pres_wins_by_state.csv and engineering additional columns
  * **natl_data_clean.ipynb** - cleans data on winning candidate from each election and exports data to pres_wins_by_election.csv
  * **state_data_clean.ipynb** - cleans data on state votes in each election and exports data to pres_wins_by_state.csv
* **data** - output data generated by code directory files for use as Tableau data sources
  * **pres_wins_by_election.csv** - contains year, winning candidate, winning party, and whether the winning party flipped the presidency for every election
  * **pres_wins_by_state.csv** - contains state, year, party that won each state, and whether the winning party flipped the state for every election
  * **state_flip_data.csv** - contains pres_wins_by_election.csv and pres_wins_by_state.csv merged by year and binary columns denoting each party's state wins to offload calculations from Tableau
* **graphics** - Inkscape SVG source files for site logo and favicon
* **raw_data** - unaltered CSVs converted from Wikipedia tables
* **site** - all HTML for the main project site
