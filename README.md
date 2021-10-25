<!--- STARTEXCLUDE --->
# Astra DB Loom
*60 minutes, Advanced, [Start Building](https://github.com/DataStax-Examples/astra-loom#prerequisites)*
<!--- ENDEXCLUDE --->

![image](https://raw.githubusercontent.com/DataStax-Examples/astra-loom/master/hero.png)

Loom is a thread based chat server, where users can send messages to one or more threads via hashtags (ex. "I'm heading to the park at noon #family #friends #frisbee_club" ).  Users can subscribe to new threads they see by clicking them and start new threads but just adding a new hashtag to a message.
  
## How this works
The app demonstrates working with DataStax Astra DB, Elixir, and Phoenix Liveviews together. The project attempts to make the best use of this stack.  Messages histories are saved and loaded in Astra DB, while new messages are shared via Phoenix channels between all active users in a "thread".  The goal is a fast, scalable, and durable chat/messaging application.

## Get Started
To build and play with this app, follow the build instructions that are located here: [https://github.com/DataStax-Examples/astra-loom](https://github.com/DataStax-Examples/astra-loom#prerequisites)

<!--- STARTEXCLUDE --->
# Running Astra DB Loom
Follow the instructions below to get started.

## Prerequisites
Let's do some initial setup by creating a serverless(!) database.

### DataStax Astra
1. Create a [DataStax Astra account](https://dtsx.io/38DEkDw) if you don't already have one:
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-register-basic-auth.png)

2. On the home page. Locate the button **`Create Database`**
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-dashboard.png)

3. Locate the **`Get Started`** button to continue
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-select-plan.png)

4. Define a **database name**, **keyspace name** and select a database **region**, then click **create database**.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db.png)

5. Your Astra DB will be ready when the status will change from *`Pending`* to **`Active`** 💥💥💥 
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-active.png)

6. After your database is provisioned, we need to generate an Application Token for our App. Go to the `Settings` tab in the database home screen.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings.png)

1. Select `Admin User` for the role for this Sample App and then generate the token. Download the CSV so that we can use the credentials we need later.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings-token.png)

1. After you have your Application Token, head to the database connect screen and copy the connection information that we'll need later. We'll replace `ASTRA_DB_APPLICATION_TOKEN` with the `Token` value that is part of your Application Token.
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-connect.png)

### Github
1. Click `Use this template` at the top of the [GitHub Repository](https://github.com/DataStax-Examples/astra-loom):
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-use-template.png)

2. Enter a repository name and click 'Create repository from template':
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-create-repository.png)

3. Clone the repository:
![image](https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-clone.png)

## 🚀 Getting Started Paths:
*Make sure you've completed the [prerequisites](#prerequisites) before starting this step*
  - [Running on your local machine](#running-on-your-local-machine)
  - [Running on Gitpod](#running-on-gitpod)

### Running on your local machine (Docker)
1. See https://hub.docker.com/repository/docker/omnifroodle/astra-loom for information about launching the astra-loom docker container.

2. Copy `example.env` to `.env` and update it with your Astra DB and Google credentials.

3. Run the following to setup your environment:
```bash
source .env
mix deps.get
cd assets && npm install
mix loom.init
```

4. To start the server
```bash
source .env
mix phx.server
```

### Running on Gitpod
_NOTE: You can skip any Google auth setup on gitpod.io, setting up Google auth on gitpod is beyond the scope of this document._
1. Click the 'Open in Gitpod' link:
[![Open in IDE](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#https://github.com/datastax-examples/astra-loom)

2. You will be prompted for the following:
* "ASTRA_ID" - This is your Astra DB ID, you can find this on the Astra DB web dashboard
* "ASTRA_REGION" - The region where your Astra DB is hosted, this is also on the Astra DB web dashboard
* "ASTRA_USERNAME" - The username for you Astra DB
* "ASTRA_PASSWORD" - The password for your Astra DB username

3. The webserver should start automatically in a new window or tab of your browser.

4. Open a terminal and initialize your Astra DB schema with the following command:
```bash
mix loom.init
```

5. Click "Random Dev User" to login with a random identity and look around.
6. <!--- ENDEXCLUDE --->
