civic.json - A standard metadata specification for civic technology projects
This file lives at 

1-Purpose

	Civic.json is a metadata standard for civic technology projects that is intended to complement project information in a github repository.  This document will specify the keys and values that make up the civic.json data standard, and provide information about the scope, mission, and background of the standard.
	
2-Background 

	In 2013, civic Technologists at Chicago's Opengov Hacknight created a "hands-off" projects page using the github API.  In the world of civic hacking, projects come and go, and there is a risk of user-maintained projects pages to become stale.  The intent was to make a "stupid simple" projects page, where all of the data came from github repositories, where "...humans will be responsible for one thing: deciding what gets tracked."  

	The standard set of api-queryable attributes on a github repo includes name, description, contributors, creation and update info, etc, but is missing several key elements that would be useful to a projects listing.  Among these are a thumbnail photo, category tags, type of project(web, mobile, policy doc, dataset, etc).  

	Civic.json is meant to provide a standard set of metadata that resides in a common location in all repos and is accessible via the github api.  Individual project owners can create and update civic.json at will, so the projects pages can remain hands-off.

	In theory, if civic technology groups adopt this standard, it will be possible to aggregate nationwide, regional, or topic-specific lists of civic tech projects.


3-File Location and contents

	3.1 civic.json shall reside in the root directory of a project's github repository.
	3.2 civic.json shall include a single object represented as JSON, with the key/value pairs outlined below.
	3.3 

4-Key/Value Specification

	4.1 "status", text indicating the status of the project.  Any text is allowed, but a selection from the recommended values is advised:

	"Ideation" - Brainstorming phase
	"Alpha" - Brainstorming phase
	"Beta" - Brainstorming phase
	"Production" - Finished Product, development ongoing
	"Archival" - Finished Product, development ongoing
		
	4.2 "thumbnailUrl" - a url to an image associated with the project listing

	4.3 "bornAt" - text indicating the name of the event the project was conceived at, if any.  Any text is allowed.

	4.4 "geography" - text indicating the city, state, county, or other geographic entity this project is relevant to.  Any text is allowed.

	examples: "NYC", "Greater Baltimore", "South Boston"

	4.5 "politicalEntity" - text indicating the political entity the project is relevant to. Any text is allowed.

	examples: "NYC City Coucil","Chicago Department of Public Works"

	4.6 "type" - text describing the type of project.  Any text is allowed, but a selection from the recommended values is advised:

	"Web App"
	"Mobile App"
	"Policy Document"
	"Dataset"

	4.7 "needs" - an array of "need" objects.  There is no limit to the number of needs included in a project.

	4.8 "need" - text indicating a need of the project.  This can be a skillset that is needed, or any other resource.  Any text is allowed.

	examples: "Web Designer", "Web Hosting", "Political Sponsorship"

	4.9 "categories" - an array of "category" objects.  There is no limit to the number of categories included in a project.

	4.10 "category" text indicating the category of the project.  Any text is allowed.

	examples:  "Land Use", "Transportation", "Politics", "Financial", "Open Data"

5-Example civic.json

	{
	        "status": "Beta",
	        "thumbnailUrl": "http://www.skyspaceinternational.com/yahoo_site_admin/assets/images/NYC_Skyline_Thumb.97220225.jpg",
	        "bornAt": "BetaNYC Hacknights",
	        "geography": "NYC",
	        "politicalEntity":"",
	        "type":"Web App",
	        "needs": [
	                {"need": "Web Designer"},
	                {"need": "Node Dev"},
	                {"need": "Angularjs Dev"}
	        ],
	        "categories": [
	                {"category": "Community"},
	                {"category": "Education"}
	        ]
	}


6-Links

	Opengovhacknight's projects page:
	http://opengovhacknight.org/projects.html


	Repo for backend of Opengovhacknight's projects page:
	https://github.com/open-city/civic-json-worker

	Repo for frontend Opengovhacknight's projects page:
	https://github.com/open-city/open-gov-hack-night#projects-and-people

	BetaNYC's projects page:
	http://projects.betanyc.us

	Repo for BetaNYC's projects page:
	https://github.com/chriswhong/betanyc-projects-list




