We are Crowdfunding group: Nghia, Anna, Yukun, and Madeleine. To make our data easier to read, here are some comments:

- We have collected the data for each category that we mentioned in the First Assignment: music, film, sport, and theatre.
- Each file named 'data_[category]_[start]_[end].csv' contains the data with 15 features of [category] from page number [start] to page number [end]
- We also extracted some additional information about the backers who chose to support each project. This information is stored in file named:
	'rewards_[category]_[start]_[end].csv
- Our code is written in file named 'collect_data.ipynb', and we keep the detail of our code on github: 
	https://github.com/nghiadanh26/Crowdfunding.git 
- We are using Selenium to load a page, that takes much time because we wait for loading page for a constant amount of time. We are trying to detect when a page is fully loaded
