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

Let's take a look at `store_pages.tmpl`.

Yext Sites uses Go’s html/template as the basis for templating. Data from the Stream is accessible in the template file using Go variables. Stream data will be explained in more detail later.  

For now, go ahead and make a change to the template:


{{< code lang="html">}} <html> 
	<body> 
	  <h1> Store Details </h1>
	  <h2>{{.name }} </h2>
	  <p> {{.address }} </p>
	  <p> {{.phone}} </p>
      <p> Hello world </p>
	</body> 
</html> {{</ code>}}

Saved changes will live reload in your browser. 

##### Step 4. Commit and push your changes  
Let's deploy your changes . 

Commit and push up to the origin. 

{{< code lang="js" >}} git push u- origin master {{</ code >}}

By default, Yext Sites is set to auto-deploy from the repo that you've linked.  

Open the Yext Dashboard and you should see a new deployment initalizing. 

![second](/images/second_deploy.png)


Yext is building a new version of your site based on your updated template. We call this a deploys.  

Deploys are the fundamental building blocks of your deploy workflow. Each deploy is an independant, fully rendered version of your site. Each deploy can be previewed at unique preview URL. Open your deploys in new tabs and try to find the 

##### Step 5. Rollback to your previous deploy  
By default, your most recent deploy is published to the main URL of your site. You should see the deploy you just pushed with a "published" pill next to is in the UI. 

Yext allows you to rollback to previous deploys in seconds. Let's take a look at how this works. 

1. Open the main URL of your site and note how it reflects the template changes you just made. 
2. Now publish the previous deploy from the Yext Dashboard. 
3. Refresh the production url. You should see the older, unedited version of your template live. 

The deployment pipeline is designed to make your development safe and efficient. Learn more here. 


**What's next?** 
Let's dive into Yext Streams - the mechanism for sending data to your website.  

