# Spotanalyst

⚠ _**For other Detailed Information visit our Wiki Page: [Click Here](https://github.com/VijayasaiVS/spotanalyst/wiki)**_

## Initial Setup

### Installation:

1. Git clone: [Github Link](https://github.com/VijayasaiVS/spotanalyst.git)

2. In Terminal, 
              _pip install -r requirements.txt_ 
   to install the pre-requisites

### Setup ENV & Spotify Developer Account:

🔴 **Create 2 env files at:**
       1. _**prediction/.env**_
       2. _**webapp/server/.env**_

  *   **Setup ENV at prediction/.env:**

        1. Login with Spotify Developer [Click Here](https://developer.spotify.com/dashboard/) 

        2. Create a new App on Spotify Developer Console
            * Create a New App [#1](https://imgur.com/a/JjOiss1)
            * Collect Spotify Client ID, Secret and also set Redirect URI in "Edit Settings" [#2](https://imgur.com/a/zwZobZj)

        3. Save those details in _prediction/.env_

       `prediction/.env should look like this:`

               SPOTIFY_CLIENT_ID=<spotify cliend id>
               SPOTIFY_CLIENT_SECRET=<spotify client secret>
               REDIRECT_URI=<redirect uri for spotify app>
               SCOPES=user-read-currently-playing user-library-read user-top-read user-read-playback-position

   *   **Setup ENV at webapp/server/.env:**

        1. Edit the .env file at _webapp/server/.env_

        2. Set same client id, client secret, redirect uri, scope from _prediction/.env_

        3. **Setup Chart Studio:**

             * Create a chart studio account [Click Here](https://plotly.com/chart-studio/)

             * Get the API Key from here [Click Here](https://chart-studio.plotly.com/settings/api)

         4. Edit the details on _webapp/server/.env_ with respective data

         `webapp/server/.env should look like this:`

               SPOTIFY_CLIENT_ID=<spotify cliend id>
               SPOTIFY_CLIENT_SECRET=<spotify client secret>
               REDIRECT_URI=<redirect uri for spotify app>
               SCOPES=user-read-currently-playing user-library-read user-top-read user-read-playback-position
               HOSTNAME=localhost
               PORT=9090
               SESSION_TYPE=memcached
               SECRET_KEY=<some random characters as secret key>
               PLOT_USERNAME=<plotly username>
               PLOT_API=<plotly api key>
               FILESERVER=<full path to the predicted csv file>


***


## Create Prediction Model

1. Run _song_feature_predict.ipynb_

2. Make sure a _.pkl_ file is made finally


***

## Front End

### Run App:

1. Setup correct location of training model and make sure every field is changed as per instructions.

2. Run _app.py_ to start the app

3. If everything goes well, your app will be posted at [http://localhost:9090](http://localhost:9090)
