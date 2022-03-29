# Deploying Backends to Heroku

## Objective

Deploy our Express JS server and a MySQL DB to Heroku.

## Preparing the Server

### Before we start

- Do you have your code ready to deploy on your `main` branch?
- Do you already have scripts in `package.json` to migrate and seed your database?
- Do you have a script that runs when using `npm start`? (It specifically looks for it)
- Have you install the cors middleware?

### Configuring Heroku

- [ ] Download the Heroku CLI
- [ ] Use `heroku create` to create a new Heroku instance
- [ ] Login to your [Heroku dashboard](https://dashboard.heroku.com), choose Resources, Search for "JawsDB MySQL" (NOT JawsDB Maria) in Add-Ons. Choose "Kitefin Shared - Free" account.
- [ ] Verify you have access to the connection string.
  - If you type `heroku config` it should appear as a config variable named `JAWSDB_URL`; will we use this inside `/server/knexfile.js`.

### Editing our Backend Code to take a production Database

- [ ] Modify `/server/knexfile.js`
- [ ] Modify `/server/db.js`

### Deploying code to Heroku

- [ ] Make sure your changes are committed on your `main` branch
- [ ] Deploy to Heroku from the CLI:
  ```bash
  git push heroku main
  ```

### Migrating and seeding DB data on production

We will need to migrate the database on production so it takes the appropriate tables.

Near the top right of your Heroku Dashboard, there should be an option that says "More". Click More and you should see a dropdown of options, click "Run console" and follow the prompt, entering the word `bash` and hit run. Running the console will log you into your applications server via shell/command-line. This is handy as it will allow you to run npm and bash commands.

You can also run this in command line via `heroku run bash`:

```bash
$ heroku run bash
Running bash on ⬢ q1-2022-palm-testrun... up, run.3372 (Free)

$ npm run tables:migrate
> crud-demo@1.0.0 tables:migrate
> knex migrate:latest
Using environment: production
Batch 1 run: 3 migrations

$ npm run tables:seed
```

An API should run on https://[HEROKUAPP].herokuapp.com/api/v1/warehouses

NOTE:
Not working? Turn it off and on again! `heroku restart`

## Preparing the Client

### Before we start

- Are you calling your backend directly? If so we'll have to move it to an environment variable.
- Edit code so any calls to the backend use environment variables
  - The environment variables should be prefixed with `REACT_APP_`

### Deploying to Netlify

- Make sure your environment variables are set there as well
  - REMINDER: if you make changes to your environment variables you MUST redeploy

## Resources

- https://daveceddia.com/deploy-react-express-app-heroku/
