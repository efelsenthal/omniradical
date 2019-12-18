
#omniradical.com

omniradical is open source site generation software built on the Amazon serverless framework application model

## why

The goal is software that can accept written or spoken words to generate the common components of software applications which work together to function as application software.
To do this, we are going to use a chatbot and software generation.
Toolset:  Git, SAM, Lambda, API Gateway, NoSQL, Relational DBs, Reporting, S3, Glue and more
Getting paid: Roadmap to getting paid is open to discussion.

## who can work on this
Anyone can clone this project and make a pull request.

## the language (for starters)

Make app (app name) makes an app  
Make user (user name) makes a user  
Give public access to app name  
Give user access to app name, entity name or field name  
(entity name) has a (entity name) makes a 1:1 relationship  
(entity name) has (entity names)  makes a 1: m relationship  
(entity name) is a/an (entity name) creates an inherited table, field type  
Make a report of [entity [entities]] [as a list] [as an item]  
Add report (report name) to page (page name)  


## initial development sequence

1) Add the ability to publish the site as Hello World from a this Git master branch
   I NEED SOMEONE TO DO THIS (me for now)  
   1a)write a node.js lambda function that takes as input an app name (string) and creates an omniradical.com AName using AWSSDK, then follows this procedure to create an API https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-edge-optimized-custom-domain-name.html  
   1b) the api will map to a copy of existing hello world API gateway, but it will say hello world from app {appname}  
   1c) import the lambda function into SAM  
   1d) Add an input box and submit button (this to be replaced by chatbot later) into existing main web page so that one can create a new app by clicking submit and then get a message "Your app is being created at {appname}.omniradical.com/home.  Please try accessing it in a few minutes.  
2) Give the Hello World a chat bot.
3) Respond to "Make app (app name) by deploying a new URL in the form https://appservername.omniradical.com who's header is [app name] and is visible to the public.
4) Respond to "Make user" by creating a 2 factor Cognito user.
5) Respond to "Give user access to [app name]" by updating the app so that it can accept a user login for this user and after logging in the page will display "logged in as [user name]" and a logout menu item will be added.



## Starting documentation taken from SAM template lambda-web-page

# lambda-web-page

This component creates an API Gateway endpoint that is linked to a Lambda function that returns HTML (i.e. page can be viewed in a web browser)

## Intallation

Install this component from the [AWS Serverless Repository](https://serverlessrepo.aws.amazon.com/#/applications/arn:aws:serverlessrepo:us-east-2:494028075635:applications~lambda-web-page-example) 

## Local development

To use / modify etc the source code you can get started by:

1.  Clone this repo

2.  From the command line navigate to the `/lambda` folder and run `npm run mock`.  This will mock the html response by creating an HTML file as `mock/mocked-response.html`

3.  This component can be built using AWS Codebuild.  Use the `buildspec.yaml` template if building using Codebuild


     


