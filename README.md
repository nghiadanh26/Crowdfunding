# Crowdfunding project
## Information about our group
This is a project of the course MODS203, we are crowdfunding group, with: Nghia, Anna, Yukun, and Madellein.
## Step 1: Collect data
### 1.1 Overview of our work
In order to collect data from website: https://www.kisskissbankbank.com/en/discover we used BeautifulSoup and Selenium. For BeautifulSoup, it's quite simple, but with Selenium, it's more complicated and takes much time to work with. That is because, Selenium needs to open a new Chrome browser to load Javascript data. For each project, we have to open three tasks of Chrome, thus, it takes time to wait for web loading and scarping data.
In general, it takes us about 6min for obtaining 9 observations with full features. There has been a little bit difference between the features we stated on the Assignment 1 due to the feedback of the professor. Now, we have these features:

    'id'                    : ID of project
    'is_successful'         : project is successful of not
    'percentage_fund'       : Equal to 100*funded/target. If it is greater or equal than 100, the project is successful
    'funded'                : Amount of money the project was funded, in euros
    'target'                : Amount of money the project hopes to be funded, in euros
    'in_2020'               : If the end date of the project is in 2020, this variable will be True, and False otherwise
    'backers'               : The number of backers for this project
    'category'              : Category is one of these four categories: Music, Sport, Film, and theatre
    'thumbnail_type'        : Image or Video
    'num_rewards'           : The number of offered rewards for backers
    'min_price'             : The minimum price of a reward that the backers can get, in euros
    'max_price'             : The maximum price of a reward that the backers can get, in euros
    'num_news'              : The number of news of the project
    'num_comments'          : The number of comments of the project
    'num_contributions'     : The number of contributions of the project
    'num_creator_projects'  : The number of projects created by this project’s creator

Besides the main data above, we also collected the information about the ranges of prices of each project and the number of backers supporting each price. This means we have another data:

    'id'        : ID of project
    'category'  : Category is one of these four categories: Music, Sport, Film, and theatre
    'price'     : one price that backers can choose
    'backers'   : number of backers choosing for this price
    
### 1.2 Understand the code
In this folder, we created some important files:

    'collect_data.ipynb': Code to collect data from website
    'test_selenium.ipynb': Code to play with selenium, if you are not familiar with it
    'chromedrive.exe': Driver for openning Chrome using Selenium
    'data' folder: Containing the data we have obtained
    
Let me explain a little bit about the our main code in file 'collect_data.ipynb'. In this file, we wrote some functions:

    create_url(page, category): create the url based on page number and filter parameters
      param:
        page: int, the page we want to scrape
        category: str, the category we want to filter
      return: str, the url
    
    get_page(url): Get the page from url, using the request package
      param:
        url: str, the url to get page
      return: bs, BeautifulSoup containing the page
      
    get_num_of_projects(bs): get total number of projects matching the filter
      param:
        bs: bs, BeautifulSoup containing the page
      return: int, the total number of projects matching the filter
      
    get_num_of_pages(bs): get total number of pages matching the filter
      param:
        bs: bs, BeautifulSoup containing the page
      return: int, the total number of pages matching the filter
      
    go_to_project(url_pro): Go to each project and take the project's information
      param:
        url_pro: str, url of the project
      return:
        'num_rewards'           : int, The number of offered rewards for backers
        'min_price'             : float, The minimum price of a reward that the backers can get, in euros
        'max_price'             : float, The maximum price of a reward that the backers can get, in euros
        'num_news'              : int, The number of news of the project
        'num_comments'          : int, The number of comments of the project
        'num_contributions'     : int, The number of contributions of the project
        'num_creator_projects'  : int, The number of projects created by this project’s creator
        'prices_np'             : numpy array, list of prices of the project
        'backers_np'            : numpy array, list of backers supporting each price of the project
        
    collect_data(start, end, category): Collect the data and store into DataFrame
      param:
        start: int, the start page
        end: int, the end page
        category: str, the category we want to filter
      return:
        samples: list, containing the main data
        rewards: list, containing the information about the rewards
        
### 1.3 Run the code
Before running the code, make sure you had all the packages in import part. And, you also need the Chrome browser to run with Selenium. Finally, run it.

## Step 2: Clean the data
(Coming soon)
