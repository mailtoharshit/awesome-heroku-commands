
# Awesome Heroku Commands
-- A curated list of delightful Heroku Commands


<img src="images/heroku.png" align="center" width="1200">

# Heroku Command Line
The heroku command-line interface (CLI) is a tool that wraps the Heroku Platform API, providing support for things like creating/renaming apps, running one-off dynos, taking backups, configuring add-ons and managing your app’s state-all from the terminal. Install it by following the instructions in Heroku Command Line.

The heroku command-line interface (CLI) is a tool that wraps the Heroku Platform API, providing support for things like creating/renaming apps, running one-off dynos, taking backups, configuring add-ons and managing your app’s state-all from the terminal. Install it by following the instructions in Heroku Command Line.

## Download and install

#### OS X Homebrew

To install the Heroku CLI with [homebrew](http://brew.sh/):

```
$ brew install heroku
```

#### OS X Installer

Download and run the [OS X Installer](https://cli-assets.heroku.com/branches/stable/heroku-osx.pkg).


#### Windows

Download and run the Windows installer [32-bit](https://cli-assets.heroku.com/branches/stable/heroku-windows-386.exe) [64-bit](https://cli-assets.heroku.com/branches/stable/heroku-windows-amd64.exe)

#### Verify your installation
To verify your CLI installation use the heroku --version command.

```
$ heroku --version
```

You should see heroku-cli/x.y.z in the output. If you don’t, but have installed the Heroku CLI, it’s possible you have an old heroku gem on your system.

## Getting started

You will be asked to enter your Heroku credentials the first time you run a command; after the first time, your email address and an API token will be saved to ~/.netrc for future use. Here at Intuitive Surgical, you will need to login via single sign on.
        heroku login --sso

#### List all Heroku apps
```
$ heroku apps
```

#### Create apps with a specific name

```
$ heroku create myapp
```

#### Create app with a specific name and within an organization

```
$ heroku create myapp --org intusurg
```

#### Deploying from your local branch to heroku and force build

```
$ git push heroku localbranch:master (mybranch: master)
```

#### Rename apps

```
$ heroku heroku apps:oldname newname
```

#### Add heroku remote to existing project

```
$ cd myapp
$ heroku git:remote -a heroku-remote-name
$ git remote -v
```

#### Open current heroku app in browser

```
$ heroku open
```


#### Open application config

```
$ heroku config
```


#### Show state of the app

```
$ heroku ps
```

#### Open application logs

```
$ heroku logs
```

#### Push/pull database (proceed with caution)

```
$ heroku db:pull
$ heroku db:push
```

#### Scale web app or add new dynos

```
$ heroku ps:scale web=1 // 1 is number of dynos the app will use (web=2 for two dynos)
```


#### Clone heroku app to local machine

```
$ heroku git: clone -a myapp
```

#### Heroku Addons

```
$ heroku addons
```

#### Delete all heroku apps (be very careful)

```
for app in $(heroku apps); do heroku apps:destroy --app $app --confirm $app; done
```

#### Setting an application in the org

```
$ heroku config:set --app myapp --org=intusurg
```

#### Setting environment for the applications

```
$ heroku config:set NODE_ENV=production
```

#### Setting environment for application in the org

```
$ heroku config:set --app=myapp NODE_ENV=production
```
#### Deploy new release and rollback (be careful)

```
$ heroku releases
$ heroku releases:rollback v#### (rollback to #### version)
```


## Postgres Commands

#### Postgres info

```
$ heroku pg:info
```

#### Continuously watch heroku

```
$ watch heroku pg:info
```


#### Establish session with remote database with psql

```
$ heroku pg:psql mydatabase  // my database is your remote database
```
