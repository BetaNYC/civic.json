**UNDER DEVELOPMENT**

This standard is still being refined. [Join in on the discussion!](https://github.com/chriswhong/betanyc-projects-list/issues/5)

---

Civic.json is a metadata standard for describing civic technology projects. They are tiny json files that capture the essential of a project - it's name, github repo url, website url, contributors, thumbnail, topic, and so on.

The initial use case is to make it easy for civic hacking groups to track their projects, and display them in [project](http://opengovhacknight.org/projects.html) [pages](http://projects.betanyc.us/#!/) - plenty of others are expected to emerge.

Instead of forcing developers to manually assemble a civic.json files for their project, our goal is to make robots do as much of the work as possible.

*For the story behind civic.json, [read this](https://hackpad.com/Civic.json-planning-meeting-EusFEMPgMio#:h=Chicago's-Open-Gov-Hack-Night-). For our design philosophy, [read this](https://hackpad.com/Civic.json-planning-meeting-EusFEMPgMio#:h=Civic-json-worker:-way-forward).*

## civic-json-worker
[civic-json-worker](https://github.com/codeforamerica/civic-json-worker) is an API that eats a project's github repo url and spits out a civic.json file for it. Most of the fields describing the project are fetched from the github API (**github fields**), a small set of **extended fields** have been proposed.

Project pages submit github repo urls to the system, and then retrieve civic.json files form for it [display](opengovhacknight.org/projects.html).

The API is live, and under active development by Code for America and Open City, contribute [here](https://github.com/codeforamerica/civic-json-worker/issues).

## Github fields

Here are the Github-specific fields currently being gathered by civic-json-worker:

{
        "description": "CTA Transit API", 
        "contributors": [
            {
                "owner": true, 
                "login": "harperreed", 
                "avatar_url": "https://gravatar.com/avatar/b7a96b3d5b5cfed5228396104cd67b38?d=https%3A%2F%2Fidenticons.github.com%2F2f810d47ed84f11f7009b39ddc3bed95.png&r=x", 
                "contributions": 8, 
                "html_url": "https://github.com/harperreed"
            }
        ], 
        "contributors_url": "https://api.github.com/repos/harperreed/transitapi/contributors", 
        "forks_count": 1, 
        "html_url": "https://github.com/harperreed/transitapi", 
        "updated_at": "2013-12-29T00:30:51Z", 
        "project_needs": [], 
        "owner": {
            "login": "harperreed", 
            "avatar_url": "https://gravatar.com/avatar/b7a96b3d5b5cfed5228396104cd67b38?d=https%3A%2F%2Fidenticons.github.com%2F2f810d47ed84f11f7009b39ddc3bed95.png&r=x", 
            "type": "User", 
            "html_url": "https://github.com/harperreed"
        }, 
        "id": 296568, 
        "name": "transitapi", 
        "language": null, 
        "created_at": "2009-09-03T16:08:49Z", 
        "pushed_at": "2011-11-20T23:51:23Z", 
        "watchers_count": 6, 
        "open_issues": 0, 
        "homepage": "http://harperreed.github.com/transitapi/", 
        ]
    }



## Extended fields
Out of the box, the Github API lacks a few very useful fields - a civic tech project's topic, need, type, and so on. 

There is a lot of interest in collecting this extra data. To make that practical, we need to select a very small set of essential extended fields, and try to incentivize and faciliate their collection as much as possible.

Here are some of the *proposed* extended fields:


	{
	        "status": "Beta",
	        "thumbnailUrl": "http://www.skyspaceinternational.com/yahoo_site_admin/assets/images/NYC_Skyline_Thumb.97220225.jpg",
	        "type":"Web App",
	        "needs": [
	                {"need": "Web Designer"},
	                {"need": "Node Dev"},
	                {"need": "Angularjs Dev"}
	        ],
	        "topic": [
	                {"category": "Community"},
	                {"category": "Education"}
	        ]
	}


# Contribute
Civic.json is just a proposal right now. Here's what needs to happen for it to become a reality.

* Discuss and decide on extended fields (being discussed in the issue tracker).
* Brainstorm practical ways to gather extended fields (being discussed in the issue tracker).
* Decided whether we want to align civic.json fields with schema.org (being discussed in the issue tracker).
* Once fields are settled, make civic-json-worker [dump project info in civic.json format](https://github.com/codeforamerica/civic-json-worker/issues/13). 


