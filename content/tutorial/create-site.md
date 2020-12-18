+++
title = "1. Create and Deploy Your Site"
description = ""
+++

{{< lead >}} The goal of this tutorial is to create and deploy a Site that is hooked up to the Yext Knowledge Graph. To do so, you will create a Yext Site project in Git, set up your Yext account, and hook the two up. Let's do this!  {{< /lead >}}


##### Before you begin
You will need a Yext account to go through this tutorial. Don't have one? Sign up for a free Yext account [here](yext.com) 


##### Step 1. Clone the Yext Sites Starter Repo 
Yext lets you link a Github repository to your Yext account for continous deployment. Each time you push to your Github repo, Yext will deploy your latest commit. 

Create a new repo in your Github account and clone the Yext Starter repo. 

{{< code lang="js" >}} git clone github.com/gideonwhylr/yext-sites-starter-v1 {{< /code >}}

*First time working with git?* Check out our step-by-step guide [here](yext.com) and return to this point. 

##### Step 2. Set up your Yext Account with Solution Template 

In this step your going to set up your Yext account so its ready to deploy a site. You will do this by applying a [SolutionTemplate](yext.com) to your Yext account, which will install sample data to help you get going. Don't worry - you can edit all of the data later.  

Navigate to the Apps tab and find the Solutions sub-tab. Open the Basic Template and install it! 

![solution](/images/solution_template.png)

Your yext account should look something like this: 
![default](/images/yext_default.png)

##### Step 3. Create a Site and Link it to Your Github account 

Open the Sites tab in Yext and create a new Site

![create-site](/images/2020-12-17_19-11-37.png)

Connect to your Git account and choose your repo with the Yext Sites starter. 

![connect](/images/2020-12-17_19-15-24.png)

Continue through the setup and create your Site! 


##### Step 4. Check Out Your Newly Deployed Site! 

And you're Live! 

Yext has deployed your Starter Site based on data in Knowledge Graph. Open your site in a new tab to see what it looks like. Whenever you edit data in the Knowledge Graph, Yext will automatically update the relevant pages. 

*Let's try it.* 

Open an entity in the Knowledge Graph and update a data field. Yext will automatically stream the update to your web-pages in seconds. Yext Sites is designed to process thousands of updates in seconds. 


**What's next?**  
 - Tutorial 2: Edit a template for your Site
 - Tutorial 3: Edit what data is streamed to your Site 