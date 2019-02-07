# Selfscape
__Personal data on your edge of the network__

![Selfscape](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/logo.png )

As part of the presentation '#10YEARdataCHALLENGE' on how to manage and get insight from our data stored in different silos, I introduced a simple Electron that gives users a friendly interface to browse personal contents. 

In a previous talk I showed how I used [Splunk](https://www.splunk.com/) for creating a local index of  ~2.5 TB made by data I collected since 1998. Splunk comes with a query langauage, SPL (Splunk Search Processing Language) that allows to get refined results quickly. In the same talk I also showed how I built indexes for data that usually sits in the cloud and how I analysed them though fancy diagrams and realtime dashboards. 

![](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/public/dashboard.png)

Splunk offers an intuitive web app to navigate and query data but accessing several thousands of events from scattered sources required an easy and usable interface like browsers do for the Internet.
The PoC for the presentation is named Selfscape after Andeersen and Horowitz's Netscape browser. 
The search bar converts user inputs in a Splunk Queries and posts them to a Splunk instance though the API. 
The results are filtered and presented trying the best to enphasise meaningful contents.  

![Selfscape_architecture](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/public/selfscape.png)

Indeed, one of the (yet unsolved) challenge is facing such a system is prioritsing results. 
Keeping the analogy with the Internet, web-page prioritisation was handled by Larry Pag and Sergey Brinn's Page Rank. 
Last part of the presentation shows an adaptation for an event page rank that can be applied to the 'Internet of Self' scenario. Page Rank builds the result set by scoring candidate web pages wrt the number of references in other pages. 

![](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/public/pagerank1.png)

Events containing timestamps and geolocation metadata (e.g. EFIX metdata) get an higher rank events if other events metadata are in a related time interval and within a specific geo range.     

![](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/public/diagram-14.png)

The markers in the pictures represent two events (e.g. two picture) that are in a specific time interval inside two different event density area. The event represented by the red marker will get an higher score than the yellow one. 

### Splunk Primers and sourcetypes

* Apple IWatch
* File System (unix)
* Google Calendar
* Google Drive
* GMAIL
* Location Data
* Facebook messages
* Monzo
* Twitter 


### Demo
The demo shows how contents are priortised for the keyword Cristmas and December 2019. 
__NOTE: This is an extremely happy case, built ad hoc to show what was the aim of this presentation._
Almost all of the time the result set is still not what we would like to present.
![](https://raw.githubusercontent.com/GaetanoMondelli/selfscape/master/public/screencast.gif)

