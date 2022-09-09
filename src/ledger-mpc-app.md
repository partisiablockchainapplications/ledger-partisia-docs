# ledger-mpc-app
Partisia has developed a JS application that will interface with the Ledger App here:
* [Source Code](https://gitlab.com/partisiablockchainapplications/ledger-mpc-app)
* [NPM](https://www.npmjs.com/package/ledger-mpc-app)

### Running the App
To run the app and test all the functionality of the Ledger Device please do the following:

```bash
git clone git@gitlab.com:partisiablockchainapplications/ledger-mpc-app.git
cd ledger-mpc-app

# install dependencies
npm i

# add your MNEMONIC into a .env file
echo MNEMONIC="word1 word2 word3 ..." >> .env

# unlock and open ledger to Partisia App
npm run test
```


### Example Interaction
<video width="320" height="240" controls>
  <source src="./assets/Ledger_Partisia.webm" type="video/mp4">
</video>