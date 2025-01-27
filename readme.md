# The JewishBook repository
Working on the Bibliography of the Hebrew Book and more

This repository is meant to serve the community of scholars working on the history of the Jewish Book as data: improving, augmenting, linking and exploring it. 

## you will find here:
* The MARC-XML file from the National Library of Israel of the Bibliography of the Hebrew Book database (BHB) converted to TSV  by Yael Netzer.
* A TSV of the DiJeSt-Books file: a cleaned, enriched version of the BHB, work in progress. Please join us in making it better!

## work that has been done on the BHB data to DiJeSt Books
### ontology
Many of the MARC021 fields were mapped to common ontologies, in order to produce a linked open data knowledge graph. To find out how to access and query it, see here: http://dijest.net/elinda/ .   

### date cleaning and normalization
105642 (of 107,977 records) dates (field 260C) were cleaned and normalized in order to enable machine readability. The are represented as dcterms:created in the DiJeSt ontology. The information regarding the certainty, accuracy and complexity of dates, implicit in  formulae such as "בערך", "המאה ה-", "לפני", "צנז׳" is yet to be integrated in the DiJeSt file, as well as field 912 (gematric date expressions). 
### place cleaning, normalization and linking
Over 106500 places-of-publication were enriched with Kima IDs. The 1080 normalized toponyms were reduced to under 900 place IDs, which are mostly georeferenced.  
For example: The Judeo-Arabic commentary on JOB, record no. 318464, which had "בודאפעשט" as its place of publication (MARC field 260a) and was normalized as (MARC field 950) "בודפשט|Budapest", and Avodat Hakodesh, record 105675, which had "אפען" as its place of publication and was normalized as "בודפסט|Ofen", were both (along with 712 other records) enriched with the KIMA-id http://geo-kima.org/place/513.
The normalized placenames are described as MREL:PUP (https://id.loc.gov/vocabulary/relators/pup.html) in the DiJeSt Ontology.

A visualization of the mapped BHB which was enabled by this work can be found here:
https://sinair.carto.com/builder/a22bf533-49de-4470-8bae-7d8b1efb286d/embed , see also this post: http://dijest.net/map-bhb/.

### person normalization and linking
The origin of the information about the authors is the NLI authority files NNL10, which contains both persons and organizations data.
The version of the file was given to us by the National LIbrary of Israel from 2015.
The names in BHB files are not unified, and therefor one can find variations such as 
In order to unify and locate names such as 	
	
- מאהלר, מנחם אליעזר בן יצחק אשר
- מאלר, מנחם אליעזר בן יצחק אשר
who both should be mapped to NLI ID 000259084

We  transformed the MARC-XML into a table, mapping the main fields into a table
With the data found in fields: 100	(heading personal name) we used [a,9]	and the indicator to detect the language, the order the name is documents (e.g., Last-First)	Subfield c	was mapped to nameTitle. More information was collected from fields 378	(Fuller Form of Personal Name), 500	(Personal Name (R))	 and	aliases in Hebrew, Arabic, Latin and Cyrylic alphabets (400,410,430,411,451,700)
Once all variations of names were enumerated in the identity table, we mapped the names in BHB to the NLI IDs.


