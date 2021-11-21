# Election Results

## Overview of Project 

### Purpose
The purpose of our module 3 project was to help Seth and Tom submit an election audit to the election comission for voters in the County Jefferson, Denver, and Arapahoe. He wanted us to collect the total number of votes casted, the complete list of candidates who recieved votes, the total number of votes each candidate recieved, the percentage of votes each candidate recieved, the voter turnout for each county, the percentage of votes in each county, and the overall winner of the election. With VS-Code, we were tasked to write a code that would take a large csv file, and have it output the inofrmation needed in an organized and easy to read text file. 
### Data provided
With this project, we were given a csv file with 369,711 rows, with 3 columns that included the ballot ID, county, and which candidate they voted for. Before writing the code, we were given a .py file that included notes on what was needed to complete the code. Below are some of the notes that were left blank, which we were assigned to code out. 

    '# 1: Create a county list and county votes dictionary.
        county_list = []
        county_votes = {}
    '# 2: Track the largest county and county voter turnout.
        largest_county_turnout = ""
        largest_county_turnout_count = 0 
        largest_county_percentage = 0
      '# 3: Extract the county name from each row.
        county_name = row[1]
        '# 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_list:

            # 4b: Add the existing county to the list of counties.
            county_list.append(county_name)

            # 4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0

        # 5: Add a vote to that county's vote count.
        county_votes[county_name] += 1
         # 6a: Write a for loop to get the county from the county dictionary.
    for county in county_list:

        # 6b: Retrieve the county vote count.
        county_vote = county_votes.get(county)

        # 6c: Calculate the percentage of votes for the county.
        county_vote_percentage = float(county_vote) / float(total_votes) * 100

         # 6d: Print the county results to the terminal.
        county_results = f"{county}: {county_vote_percentage:.1f}% ({county_vote:,})\n"

        print(county_results)

         # 6e: Save the county votes to a text file.
        txt_file.write(county_results)

         # 6f: Write an if statement to determine the winning county and get its vote count.
        if (county_vote > largest_county_turnout_count) and (
            county_vote_percentage > largest_county_percentage
        ):

            largest_county_turnout_count = county_vote
            largest_county_percentage = county_vote_percentage
            largest_county_turnout = county



    # 7: Print the county with the largest turnout to the terminal.
    winning_county_print = (
        f"------------------------\n"
        f"Largest County Turnout : {largest_county_turnout}\n"
        f"-------------------------\n"
    )

    print(winning_county_print)

    # 8: Save the county with the largest turnout to a text file.
    txt_file.write(winning_county_print)
  
  ## Results of the Election
Based on our code, Diana DeGette won the election by recieving 272.892 votes, which was 73.8% of the total votes casted. In second place, Charles Casper Stockhman has 85,213(23%) votes and Raymon Anthony Doane finished with just 11,606(3.1%) votes. In our text file we can see that the total votes casted was 369,711, and we can also see how many votes each county casted. Jefferson county(10.5%) casted 38,855 votes, Denver county(82.8%) casted 306,055 votes, and Arapahoe county(6.7%) casted 24,801 votes. 
###Election Audit Summary
Now that we have a code written out, Seth and Tom can reuse this for future elections. Just import a different csv file with different data and run the code. As long as the csv file has the same headers and column numbers, the code will work just fine. 


  ![Election_results](https://user-images.githubusercontent.com/93295820/142777135-ca556580-faa6-4abe-ad4a-c1ba7addd73a.png)
