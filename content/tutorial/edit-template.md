+++
title = "2. Edit a Template"
description = ""
+++

{{< lead >}} The goal of this tutorial is to show how to edit the templates that define the layout and content of your pages  {{< /lead >}}


##### Step 1. Download the Yext CLI 

{{< code lang="js" >}} brew install yext {{< /code >}}

Follow the prompts in the installation. If you have a Yext account, login through the CLI. 

##### Step 2. Run your site locally 

Navigate to your site directory and run the `develop` command to build your site locally.  

{{< code lang="js" >}} cd your-site-directory 
 yext sites develop {{< /code >}}

Yext will start a development server for your site. By default, you can view it at http://localhost:800.  

The development server will hot-reload any changes you make. Try editing the homepage at src/pages/index.tmpl

##### Step 3. Edit a template 
Open the `src/templates` directory to find the templates that define the pages for your site. 

Edit `store_pages.tmpl` and make a change. 

Saved changes will live reload in your browser. 

##### Step 4. Commit and Push your Changes  
Let's deploy your changes to your production Site. 

Commit and push up to the origin. 

By default, Yext Sites is set to auto-deploy from your repo. 

Open the Yext Dashboard and you should see a new deployment initalizing. 

Yext is building a new version of your site based on your updated template. We call this a deploys.  

Deploys are the fundamental building blocks of your deploy workflow. Each deploy is an independant, fully rendered version of your site. Each deploy can be previewed at unique preview URL. Open your deploys in new tabs and try to find the 

##### Step 5. Rollback to your previous deploy  
By default, your most deploy is published to the main URL of your site. You should see the most recent deploy in your dashboard with a published pill. 

Yext allows you to rollback to previous deploys in seconds. Let's take a look at how this works. 

Open the main URL of your site and note how it reflects the template changes you just made. 

Now publish the previous deploy from the Yext Dashboard. Refresh the 


