+++
title = "Quick Start"
description = ""
+++

This guide is designed to introduce the local development experience for Yext Sites. You do not need a Yext account to get started and get a test of the development experience. 

However, the full power of Yext Sites comes from hooking your Site to the Yext Knowledge Graph. Check out the Tutorial to learn more about the complete feature set



To see all the features - create a free yext account and go to the tutorial. 

1. Install the Yext CLI 

`brew install yext`


2. Create new site

`yext sites new [name] --starter=github.com/yext/yext-sites-starter`

3. Generate sample data 

Yext Sites makes it easy to create pages programmatically based on a stream of data from the Knowledge Graph. 

To get a feel for how this works, create sample data in your local project. 

`yext sites generate-sample-data`

You should see a new /sample-data directory with some data files in it. Note this is just dummy data. Later, you will hook up your Site to a real Knowledge Graph.

4. Build your site locally 

`yext sites develop` 

Yext will start a development server for your site. By default, you can view it at http://localhost:800.  

The development server will hot-reload any changes you make. Try editing the homepage at src/pages/index.tmpl

**What’s next?**
The power of Yext Sites comes from hooking up your website to a live stream from the Knowledge Graph and leveraging our deployment pipeline. 
 - Have a Yext account already? Learn how to hook up your local Yext Sites project to your account. 
 - New to Yext? Create a free account today to unlock the power of Yext Sites 
