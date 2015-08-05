Civic.json is a metadata standard for civic technology projects that is intended to complement project information in a github repository.  This repo contains documents that specify the keys and values that make up the civic.json data standard, and provides information about the scope, mission, and background of the standard.

civic.json exists to create an api-accessible set of project attributes that complements the attributes already associated with a github repository.  These can be used to power an API-driven community projects list, such as Chicago's (http://opengovhacknight.org/projects.html) or New York City's (http://projects.betanyc.us/#!/).  

civic.json looks like this:

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
