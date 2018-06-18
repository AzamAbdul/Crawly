# Crawly
A basic web crawler written for fun

# Web Crawler Design: #
* Start from a list of start links defined in a file
	* Enqueue said link
	* Go to link
	* Parse response html for link links in queue
	* Create a link between start and each page added to the queue in a database (Possibly spawn
	Place a thread to do this and re use threads using a thread pool)
## Validation: ##
* Might want to check robots.txt on each domain
* How do i make sure I don’t end up on some dynamic page that never ends?
## Analysis ##
* Run page rank on the links in the database
## Database Schema ##
### Page table ###
* id
* Url
* Domain
* Created At

### Links table ###
* id
* Start page (id)
* End page (id)
* Words Table
* id
* Word
* Created at
### KeyWords Table ###
* Page Id
* Word id
## Random Ideas: ##
Moves page further up the queue if they are from a domain I have yet to visit
Maybe even create a web site that is a search engine
## Implementation Details: ##
### Crates: ###
* log4rs (for logging)
* hyper (for HTTP requests)
* mysql (for a mysql driver)
* html5ever (for a html parser)

