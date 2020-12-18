+++
title = "3. Edit a Stream"
description = ""
+++

{{< lead >}} In this tutorial, you will learn to control what data you are streaming to your site by configuring a stream {{< /lead >}}

##### The Problem 
In this exercize, we will focus on the location data in the graph. Right now, the only data points accesible to your Site are the name, address, and phone number of your stores. We will show you how to add a store description to your pages by adding this data point to your Stream. 

##### Step 1: Open the Yext Admin Console  

Run the following command from the Yext CLI to inspect the streams your site is using 

{{< code lang="js">}} yext streams view  {{</ code >}}

The command should open up the Yext Admin Console where you can see your Streams: 

![admin](/images/admin_console2.png)


##### Step 2: Find your Stream by looking for the relevant label   
Every stream is associated with a label. This is how you link a Stream in your Yext Account to your site. 

Find the Stream Rule with the label 'storepages' 

##### Step 3: Add data to your Stream Rule 
Stream rules define what data from Knowledge Graph you're including in the stream system. 
We can see that we're only including 3 data points in the stream. Let's add the description field, as well.

{{< code lang ="json" >}} {
  "$id": "namespace_storePagesStarter_entities",
  "$schema": "https://schema.yext.com/config/cloudstream/stream-rule/v1",
  "source": "knowledgeManager",
  "destination": "graphmerge",
  "srcRegion": "nj1",
  "dstRegion": "gcp-use4a",
  "labels": ["store_pages_starter_template"],
  "filter": { "type": ["location"], "fields": ["name", "address", "phonenumber", "description"]}
}{{</ code >}}

##### Step 4: Add the description to the scheme file 
The schema file determines the shape of the data you will send to your Site. You can implement all kinds of data transformations in this step. For now, let's simply add the description field.  

{{< code lang ="json" >}} {
  "$id": "https://schema.yext.com/schemas/mySite/locations",
  "description": "Output Schema for Location docs",
  "primaryKey": "externalEntityId",
  "type": "object",
  "properties": {
"externalEntityId": {"$ref":"https://schema.yext.com/fields/yext/externalEntityId"},
"name": {"$ref":"https://schema.yext.com/fields/yext/name" }, 
"address": { "$ref":"https://schema.yext.com/fields/yext/address" }, 
"Phone": {"$ref" : "https://schema.yext.com/fields/yext/phone" }, 
"Description": {"$ref" : "https://schema.yext.com/fields/yext/description" }, 
   }
}{{</ code >}}

Save your results. You have now added the description field to your stream. Next we'll add it to your site. 

##### Step 5: View sample data

The Yext CLI allows you to view sample data from your stream to validate that it includes what you want. 

Run the following command from inside your Sites project directory. This will overwrite contents of the `/data` directory with a sample of data from you current Stream. 

{{< code lang="js" >}} yext sites generate-data label="store_pages" {{</ code >}}

Open the `/data` directory and you should see `json` files with location data that includes a store description. Let's see what this looks like on your page. 

##### Step 6: Add the description field to your template 

Open the  `store_pages.tmpl` file and add the description field to the page 

{{< code lang="html" >}} //store_pages.tmpl 
<html> 
	<body> 
	  <h1> Store Details </h1>
	  <h2> {{.name }} </h2>
	  <p> {{.address }} </p>
	  <p> {{.phone}} </p>
	  <p> {{.description}} </p>
	</body> 
</html> {{</ code >}}

##### Step 7: Build your site locally 

{{< code lang="js" >}} yext sites develop {{</ code >}}

Open your site in your browser. You should see the store description on your store pages now! 

Note your local build is based on the sample data in your repo. Let's push this change to production to do a build based on live data in the Knowledge Graph


##### Step 7: Deploy your site

Commit and push your site and opent the Yext Dashboard. 

When your deploy is complete open the preview. You should now see store description on your store pages. 

Edit the description field in the Knowledge Manager. You should see the change automatically reflected in this new deploy. 

Open a preview of an old deploy. Note the description is not included on these pages. This old deploy represents a commit without the description field include in the page template. 

