# Repligit

This app`s only purpose is to replicate(fork) it`s github repo to the user`s GitHub profile

## Run
To run it you should have python2.7 and flask installed on your host machine
And register it as OAUTH app in GitHub. It means that GitHub provides you with "client_id" and "secret_id"
then go repo`s root and run in your shell the following:

* export FLASK_APP="repligit.py"
* export SECRET= *your secret_id*
* export CLIENT_ID= *your client_id*
* flask run

The Repligit`s workflow is:

* user goes to Repligit`s url (e.g. "localhost:5000/" (first view) )
* user clicks the "Fork" button
* user is redirected to GitHub to authorize
* user is redirected back to Repligit`s 'callback' page by GitHub with a temporary code in a code parameter
* Repligit exchanges this code for an access token with GitHub
* Repligit forks the repo via GitHub API asyncroniously

then user may check whether the request is complete
