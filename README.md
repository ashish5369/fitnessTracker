# fitnessTracker
milestone 1 will be to create for 1 user only

backend 
express and node js
db is going to be both mongo db and postgres sql, starting with mongo db , we'll store all the data there
auth is going to be done using jwt adn bycrypt js
validation using zod


DB STRUCTURE:- 3 TABLES, they are connected using a user id ,adn using this user id we can fetch/modify data for any specific user

user table

            the structure is going to be like
            name
            email
            current weight
            goal weight
            foreign key to other table where his day wise diet/sleep/water intake would be stored

thers is going to be a table for all the users that will store daywise deit that they have taken in the past and this way we can have the history to rtack the progress


current/todays data table

            one table to take care of today's info and oither that store the historty
            todays data would be :-
            calories
            protein
            carbs
            fat
            distance walked
            water drunk
            sleep 
            execercies did or not:- if did then total intensity with the weight and number of sets and what body part

history table

            adn once the day is over the data is pushed to a history table for each user whcih contains old data
            the whole data would be stored , the key is going to be date and teh value is going to be th whole data we have on the todays tabel for this users and reset the toadys table for the user


api :-

    apis we need:-
                api to add user info
        userAPI:- post/put req:-api to add todays data for that user, this  api will have the user id as the parameter
                  get req:-     api to fetch tpdays data for the dashboard showing purpose

        dayEndApi:- this api will move all teh data from current table to the history table at the end of the day, with date as the key and all the other data as value

        hisotry API:- get req :-this will get the data from histiory data tbale to display on the dashboard
                      post req:- this will a date as the input parameter and for that date we can modify certain data in the history if the user wants