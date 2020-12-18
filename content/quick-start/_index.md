+++
title = "Quick Start"
description = ""
weight = 1
+++

This quick start is intented to introduce the core local development experience for Yext Sites.  You do not need a Yext Account to get started and get a sense of how things work. 

However, Yext Sites is most powerful when you hook it up to a `Knowledge Graph` and `Stream` in a live Yext account. Head to the tutorial for a full walkthrough of the entire feature set.    

1. Install the Yext CLI 

{{< code lang="js" >}} brew install yext {{< /code >}}


2. Create new site

{{< code lang="js" >}} yext sites new [name] --starter=github.com/yext/yext-sites-starter {{< /code >}}

The starter site comes with a set of templates in the `src/templates` directory and sample data in the `/data` directory. 

Note this is just dummy data. Later, you will hook up your Site to a real Knowledge Graph.

4. Build your site locally 

{{< code lang = "js" >}} yext sites develop {{< /code >}}

Yext will start a development server for your site. By default, you can view it at http://localhost:800.  

The development server will hot-reload any changes you make. Try editing the homepage at src/pages/index.tmpl

**What’s next?**
The power of Yext Sites comes from hooking up your website to the Knowledge Graph and leveraging our deployment pipeline. 
 - Have a Yext account already? Learn how to hook up your local Yext Sites project to your account. 
 - New to Yext? Create a free account today to unlock the power of Yext Sites 
