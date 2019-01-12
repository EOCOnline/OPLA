# OPLA Site
The OPLA repository contains everything needed to roll out your own basic site for an Emergency Operations Center (EOC) organized into the standard Incident Command System (ICS) sections: Operations, Planning, Logistics, Admin (OPLA).

OPLA is also the eoc.online community's first, initial demonstration of our concept. Although FEMA's NIMS 2017 Revision (https://www.fema.gov/national-incident-management-system) documented the utiliy of other organizational structures, most EOC's likely model themselves on the standard Incident Command System organizational structure of having an Incident Commander with a Operations, Planning, Logistics, and Administration (OPLA) Sections reporting to her.

Rather than read pages of web design & architecture, just set up a copy of this site on the cloud or on your laptop and see what the current (future for now) expericnce is. 

# Feedback
PLEASE do provide your feedback, using the "Issues" tab (https://github.com/EOCOnline/OPLA/issues), so we know how to make the best system possible! Please also provide your insights on the Issues marked RFC: "Request For Comments"

# Installation
Return later (March 2019?) for instructions on how to set up your own DNN site - with many of our additions for EOC use.

For now, you can easily set up your own generic DNN website to start exploring this technology:

## Windows PC Install
We recommend NVQuickSite (https://github.com/nvisionative/nvQuickSite/wiki) as a simple way to install DNN on your Windows device. It automatically handles the details of the manual install process, documented at: https://www.dnnsoftware.com/docs/administrators/setup/index.html (The Community Edition runs well and there is no need for Visual Studio to use DNN.)

## Azure Install
Until we automate this with an automatically provisioned Docker or other Azure based container the steps are:
- Go to: https://portal.azure.com/ 
- You will need to create a Microsoft username and an Azure account - both free - if you've never ventured here before.
- Minimally you will need to set up:
1) Add a Resource Group: Select your Subscription (e.g., Free Trial) and give a name to your Resource Group. Specify a Region close to you for minimal network latency, and always use this region if necessary in the future. Refresh the page to see it. This also where you can see the costs grow over time. (A free trial should give you many weeks of access.)
2) In App Services, select Add, then search for "DNN Platform" and click the Create button. Give Your App a Name, select your subscription and existing Resource Group. Ensure you create a App Service Plan/Location that matches the location of your Resource Group! Pricing Tier S1 will run DNN in a sluggish fashon and currently has upgrade issues. We recommend a P1V2 Service Plan. (You only will pay for the amount of testing you do - so likely it will be less than the $150/month estimated price.)
3) Set up your SQL Server Database, record all the usernames & passwords
4) Access your test site!
For a real site, you may want to consider setting up additional resources:
- Staging Server (a Web App) to test new ideas before rolling them out to the main (Production Server)
- LastKnownGood Server (a Web App) to move the old Production Server to, in case there is an issue with any upgrades to a staging server
- Testing Server - if you conduct enough wild development and testing to possibly overwhelm the whole Resource Group, consider moving Testing to another, insulated, Resource Group, so your developers don't stomp on your real site!
- Storage Account: This is where your automatic backups go. They do not need to be high-response. Save some money.
5) Setup Backup frequency (up to 10x/day, or less). You may also want to set up FTP, so you can periodically download an off-site copy. This *shoudl* in the future, be able to run (slowly) on a local machine, for instance if a hurricane or earthquake takes down your Internet access for a few days - or months if you live in Porto Rico.

# Documentation
Nothing esists yet, but it should be up at some point on the GitHub wiki (https://github.com/EOCOnline/OPLA/wiki) or on our main web site: http://eoc.online. See the Feedback paragrph above for how to comment and see some of our roadmap.

# Learn More
Learn more about our chosen web framework - DNN - the most popular ASP.NET based content management system at http://www.dnnsoftware.com/docs/
