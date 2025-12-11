# W3C-Citations-Converter

The page  accept inputs  references in 3 different forms and output the information as a json form used by the W3C Recspec.

It is made by  the COGA taskforce.  We have used it to build [[https://github.com/w3c/coga/blob/main/issue-papers/biblio.js](https://github.com/w3c/coga/blob/main/issue-papers/biblio.js). which is used in all the reaserch modules  in https://github.com/w3c/coga/blob/main/issue-papers/index.html 

 

Note it is buggy. you are free to imporove it. You may need to change the input a bit, but it is still better then nothing. For example, it does not expect full stops after the authers initials. 

It  accept a few different inputs.

In the form the first item is an option list labeled form of input. the options are 
1. full citation with the order of the w3c
2. standard citation
3. other
4. laws and standards


1.  Full citation with the order of the w3c is 
 Title. Authors (Initials. Last Name.) Journal title and issue, year. URL: url.com.
For Example: Designing eHealth applications to reduce cognitive effort for persons with severe mental illness: page complexity, navigation simplicity, and comprehensibility. A.J. Rotondi, M.R. Spring, B.H. Hanusa, S.M. Eack, G.L. Haas. JMIR human factors 4:1, 2017. URL: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5247620/.

2. standard citation:

Authors (Initials. Last Name.) Title. Journal title and issue, year. URL: url.com.
for example
"Shakya HB, Christakis NA. Association of Facebook Use With Compromised Well-Being: A Longitudinal Study. Am J Epidemiol. 2017 Feb URL:https://pubmed.ncbi.nlm.nih.gov/28093386/
"

3. Other (blog post etc). expect form of the input to be:
key Name	Link	Site	Authors	Date

for example: Banking for All: Why Financial Institutions Need to Offer Supportive Banking Features	https://law.yale.edu/sites/default/files/area/clinic/document/banking_for_all_cedc.report.final.pdf	Yale Law School	Brittany Farr, PHD, Brian Cash, Annie Harper, PHD	April 2019


4. laws and standards
expect form of the input to be:
Name	Link	Site	Authors	Date
for example
key Voice Extensible Markup Language (VoiceXML) Version 2.0	https://www.w3.org/TR/voicexml20/	World Wide Web Consortium	S. McGlashan, D. Burnett, J. Carter, P. Danielsen, J. Ferrans, A. Hunt, B. Lucas, B. Porter, K. Rehor, S. Tryphonas, Editors	16 March 2004



Form of the output is 

key: {
		"title": "title text",
			"date": "date",
				"authors": [auther 1", "auther 2" ],
					"etAl": "tru or false",
						"publisher": "Lpublisher text",
							"href": "link text",
								"status": "form"
	},




note if the key is missing should make it to follow the COGA protocal. (In theory) IE:  
1 *If it is a citation (academic paper) *use the database key followed by the first author and the number the author occurred in the database. The result would look like: [RM-Smith1] (RM is the reference for mental health literary review database, smith is the primary author, and 1 is this is the first occurrence).
2. *For laws and standards *use the accepted short name in the field and record it as a key in our spreadsheet/ database. For example, WCAG1.0 or Section508. 
3. *If it is  another resource (blog, fact sheet etc)  *use the database key followed by the initials of the site/organisation name (main site, not subsites) and the number this occurred in our spreadsheet. The result would look like: [RC-WHO1] (RC is the Reference for Coga sources and literary review spreadsheet , WHO are the initials of the site, such as the world health organization, and 1 is this is the first occurrence in our spreadsheet. )
