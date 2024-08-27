# MARCO-BOLO WP1 Frequently Asked Questions

- [G] (#g-software)

Frequently Asked Questions from other project partners regarding MARCO-BOLO data management approaches

We received a few data-collecting spreadsheets and were asked to comment on those. 
These spreadsheets were aimed at 
- Collecting data sources to be used in that task’s work, and documenting the who, what, when, where, how of those data sources
- Collecting data values taken from disparate data sources (aka metanalysis), and documenting the who, what, when, where, how of those data values/sources 

The first thing we had to make clear is that these spreadsheets were not documenting data sets for the purpose of publishing those as a metadata record(s) in the MBO collection in ODIS. For that, a very specific template had to be filled.
However, they were collecting data that should become part of their published data packages, as they contained provenance information for the products that the task would create from those source data.

This FAQ is not aimed as a guide for completing the WP1 metadata template spreadsheets.

# A. Formatting spreadsheets for MBO (dataset collection or to publish as a dataset)

_1 What metadata should I include in a spreadsheet that describes a collection of datasets or is a meta-analysis?_

The specific metadata required will depend on the details of your work, however along with the necessary scientific, technical, numerical metadata that you record, you should include the following domains. 
- Where? From where did the information come? 
  - Give this as a URL/DOI that points to the actual dataset, or to the publication from where you extracted information. 
    - Note that for datasets there can be two URIs that can be used: one that points to the metadata record of that dataset (in a data catalogue/portal and including only the metadata, not also the dataset itself), the other that is the download URI for the dataset (i.e. what you put into your browser to actually download it). Sometimes these two are the same, often they are different. Please give both, as a “download URI” and a “metadata IRU”, and if they are the same you can just copy the same value into the two cells. 
  - Additionally, provide any additional specific details, such that someone else could find that same information themselves. For example, if you can only access the data by typing in some ranges in a web interface, write down what those ranges are that you set.
  - If the data are not publicly available (i.e. you cannot get to it using a browser) then record the name of the database where these data can be found, and all  specific information about where in that database the information/dataset comes from (i.e. how did you find it yourself?). 
- What? 
  - A title and description of the information/dataset; this should also be understandable to others outside of your WP. 
  - Selected keywords, taken from vocabularies (see below). 
  - Where the row is about measurements, use vocabularies and and include the units (see below). 
  - Technical details that can be given about the information/dataset could include
    - If the row describes an entire dataset, then: the data format, data size (roughly)
    - Licence of the information/dataset
- Who? Names and roles of relevant people and institutes. 
- When? What date range is covered by the dataset and/or information. Ideally, if the entire dataset from which you have taken the information has a wider date range, you should record that also.
- Why? What function in your analysis/data collection does this information fulfil?
- How? 
  - How was the information created by whoever originally made the source dataset or publication you are using? Normally this should be part of that source dataset description, and you can refer to the publication itself or the dataset’s metadata (“see DOI XX for details of provenance”). However, if you can see that no how is provided there (i.e. no description of methods and protocols that were followed is provided), then say that instead (“insufficient provenance provided”). 
  - Additionally, if your task is going to work on these data, then you need to provide the information about what you have done also. This can be recorded in a separate spreadsheet, one where you describe the work you do rather than someone else did.  

These fields should be included as columns in a spreadsheet (noting that we are assuming here that each row is a separate piece of information/data value(s)/dataset)

_2 Dealing with multi-tab spreadsheets_

If you are using multiple tabs to record different information about the same topic/objects/task, , then use internal IDs across those tabs to link the records to each other. For example, in each tab you can have a first column “internal id” or “internal dataset number” and fill that in each row. These should be always completely unique for all spreadsheets and all tabs you will ever collect. 

_3 Formatting a spreadsheet when I have to give units / controlled vocabulary terms / common information over and over again_

It is advised (below) that no cell in a spreadsheet contains more than one type of value -- a number or a unit, but not both. So the value should go in one column and the unit in the next. 
It is also recommended that every measurement is given (also) as a URL taken from a controlled vocabulary, not only as the literal, again requiring two columns.
It can also be that an entire spreadsheet is about one particular fish, or one type of measurement, or one whatever. You will be thinking “I don’t want to have a column in which I copy the same taxonomic name / measurement/ whatever into each row, over and again”.

How can I more efficiently format such a spreadsheet?

Options for values that have units:
- Have a column “water temperature” and a column “unit”. If the unit is always the same this can result in a lot of rows with the same value in it.  
- Have just a column “water temperature”, and describe the unit instead in a separate “extra metadata file”. That metadata file would look like this (but see also the next set of Options)

Column name | Column description | Unit
--- | --- | ---
Water temperature | The temperature of the water at the measured depth | Degrees Celcius

- Options for information that should be given as a term from a controlled vocabulary:
As all measurements and units should be linked to terms taken from a controlled vocabulary, you will need to either have a column for the measurement (“water temperature”) and a column for the term (“term URL”) which will have the same value everywhere (e.g. “https://nicevocabulary.eu/watertemperature”).  If the unit is always the same this can result in a lot of rows with the same value in it. 
 - Have just a column “water temperature”, and add the vocabulary term instead in a separate “extra metadata file”. The example given above would now look like this: 

Column name | Column description | Term URL | Unit | Unit URL
--- | --- | --- | --- | ---
Water temperature | The temperature of the water at the measured depth | https://nicevocabulary.ue/watertermperature | Degrees Celcius | https://nicevocabulary.eu/degreescelsius

For common information, we advise the following: 
- If everything in the spreadsheet is about one type of fish, or from one geographic location, or there is other common information (the names of people who contributed to the work, the date it was completed, the version, etc), then you should add that information in another extra metadata file. It is best not to include that in the spreadsheet itself (e.g. as a top row), at least when you come round to publishing/sharing that spreadsheet, because that breaks the rules of interoperable spreadsheets (the I in FAIR). 
- This additional metadata can then be used when you describe your spreadsheet as a dataset in the Marco Bolo collection. 
- When collecting these particular extra metadata, do not use the same “extra metadata file” mentioned above, as the formatting in this case will just be plain text. You could perhaps have an extra-metadata.csv file and a descriptive-metadata.txt file. 

# B. The use of controlled vocabularies

_1 Where and how should I use vocabularies_

- Use vocabularies for 
  - Measurements/parameters
  - Units
  - Environmental terms
  - Keywords
  - Taxonomic names
  - Instrument and platforms
  - Geographic regions
  - EOV/EBVs 

- Controlled vocabularies should be written as full URLs. Some examples

  - Temperature of the water body: https://vocab.nerc.ac.uk/collection/P01/current/TEMPPR01/ 
  - Degrees Celsius: https://vocab.nerc.ac.uk/collection/P06/current/UPAA/
  - Sediment: http://purl.obolibrary.org/obo/ENVO_00002007 (but also acceptable to use ENVO:00002007)  
  - Biodiversity: http://aims.fao.org/aos/agrovoc/c_33949 or https://vocabularyserver.com/asfa/index.php?tema=2185 (same vocab, different lookup services)
  - Solea solea: https://www.marinespecies.org/aphia.php?p=taxdetails&id=127160 from WoRMS (also acceptable urn:lsid:marinespecies.org:taxname:127160 or AphiaID:127160) together with the rank (“species”);  https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi?mode=Info&id=90069 or NCBI:txid90069 for genomics
  - CTD: https://vocab.nerc.ac.uk/collection/S04/current/S0458/ 
  - Belgium exclusive economic zone: http://marineregions.org/mrgid/3293  or MRGID:3293  

- Since the URLs are sometimes difficult for humans to read, you can chose to include both the literal and the URL, using the approach described in FAQ A3

_2 What are recommended vocabularies to use_

See question 1 for examples of what the term should look like. These examples are taken from these recommended vocabularies:
- For measurements/parameters, instruments and units: The NERC Vocabulary Server, access via https://vocab.seadatanet.org/p01-facet-search or https://vocab.nerc.ac.uk/search_nvs/
- For environmental and habitat terms: The Environmental Ontology, accessed via https://www.ebi.ac.uk/ols4/ontologies/envo 
- For Marine Regions: https://www.marineregions.org/gazetteer.php?p=search
- For Marine Species names: https://www.marinespecies.org/index.php and for genomics ones, https://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi 
- For keywords: ASFA is quite good and can be accessed via https://vocabularyserver.com/asfa/ and https://agrovoc.fao.org/skosmosAsfa/asfa/en/

_3 What if I cannot find my terms in a recommended vocabulary_

If you cannot find a vocabulary, ask WP1 for help. If we cannot, then please ensure that the term is specifically, clearly, and fully described (ask WP1 to review your descriptions). The description should allow someone to know exactly what you are talking about. 
Do not use acronyms in your description, as others will not understand these.
Where possible (keywords, habitats), use terms that are good enough rather than no term at all.
Better to be more general than more specific if choosing terms for instruments and measurements: in BODC, for example, at the bottom of the term page is a list of related terms which are broader-than or narrower-than and you can use this to hone in on a better choice. 

# C. Formatting of values

_1 How should I format numbers_

- Use the number formatting standard of ‘point’ for decimal notation, e.g 10.50 not 10,50 for “ten and a half”, as it is much easier to deal with if there is one consistent approach to numbers over all MBO work. 
- Do not enter numbers with , between the thousands 
- Bear in mind that your spreadsheet application may change the number formatting to whatever is standard for your version of that app. You should change that: e.g. in excel you can either specifically change the formatting of the column to be “text” or type a ‘ before the number (that forces excel to accept what you type) 
_2 How should I deal with units_

See FAQ A3

_3 How should I format dates, times, countries, people_

- Use ISO standards for dates (YYYY-MM-DD) and always use UTC
- You may need to modify the default date formatting of your spreadsheet application: either tell it to use that ISO format or write the value with a ‘ in front of it (excel, probably works for googlesheets also) 
- Use ISO standards also for countries (BE or BEL not Belgium)
- For all mentions of people use the first name, surname, ORCID, email, institute. For all mentions of an institute, use its full name, a URL (home page), and a ROR/EDMO ID

_4 Can I fill cells with more than one value/no values_

- If you have a list to enter in a cell, use “;” or “|” as the separator, because the “,” is the separator of the CSV (comma separated variable) format that you should be exporting your spreadsheet as
- Do not mix types of values: do not have a number and a string in the same cell (unless it is a comment)
- Never leave a cell blank - use NA if there will never be a value in there
- Never use “see above” or “see row 3” or “ “” “: when someone does a filtering on that spreadsheet, these information will be useless

# D Geographic coordinates

_1 How do I give geographic coordinates_

- Give the most specific geographic information you can: not just a site ID, but also its latitude, longitude or bounding box. 
- You can create bounding boxes with this tool: see https://wktmap.com/?8f50dfaa  for an example and to see some examples: POLYGON and POINT will be the most useful types of bounding boxes
- As well as the coordinates, indicate the Spatial Reference System (also named Coordinate Reference System, see https://en.wikipedia.org/wiki/Spatial_reference_system) you are using. Spatial software (e.g. GIS) associates data with this SRS, so you should be able to identify it. SRS can be specified by using standardised codes like EPSG (see e.g. https://spatialreference.org/ref/) or OGC codes (see e.g.https://crs-explorer.proj.org/). If you are finding a location on Google maps, then the SRS in EPSG:3857, OpenStreetMap uses EPSG:4326.
- For sites, give the unique ID of the site or use a controlled vocabulary if you want to describe the site type. Coordinates will of course also be required.  
- It is good to give both coordinates and a Marine Regions identifier (mrgid) (you can find yours by using https://marineregions.org/gazetteer.php?p=search), or the identifier of the place found in another gazetteer, like in http://www.geonames.org/, because this makes searching for those data, and grouping them with other data, easier for the database where you will eventually publish your data.

# E People and institutes

_1 What people information do I include_

See FAQ C2

_2 what institute or project information do I include_

See FAQ C2

# F Provenance

_1 What is provenance?_

Provenance is the history of an object that allows you to know how the object came to be and what has been done to it over time. 
Provenance of data are:
- How, by whom, from what, where, and when was the source data created/derived? 
  - If from biological material, this how, who, what, when, where starts from the collection/creation of that material, and how, who, what was done to extract data from that material (where did it come from, with which protocols was it collected and processed, where did it come from, who did this work?). 
  - If the source data are measurements, then how, who, what, where, and when were those measurements made?
  - If the source data were not created by you, but you got them from already-published data, then the provenance here includes the URL of that dataset’s metadata description and/or of the dataset itself, and any information about selections you did from that data (e.g. you only wanted a certain date range from the entire dataset). 
- Once the source data have their provenance, you then follow the trail of what was done to that source data to create the final data/data products that are your end result. How and with what processes/software were the data manipulated or analysed. Who did this work? Where is the software that was used and what parameters were used in the software?
- Ultimately, the provenance allows
  - someone to recreate your final data products
  - someone to trust your final data products, and hence to be able to use them 


_2 What (provenance) information should I collect as I go through my project_

- Record the origin of any source data used: where you got the data from (URL) and where the metadata record of that data can be found (if different; URL), who were the data creators and data owners, the data licence, what parameters you set if you did not download the entire dataset.
- The name of the protocols that were followed: if these are published, then their URL/DOI, if they are not then the filename and remember to publish those as part of your eventual dataset. 
- The list of parameter settings for any software you used, along with the name of the software and its version.
- Record the spatial and temporal range of the dataset - both the part you used but additionally the entire range.
- Who did the work (name, email, ORCID, and institute name and ID).
- Where and when were any material or measurements collected/made (geocoordinates, and UTC timezone or local time+time difference from UTC). 

_3 What about datasets that are not publicly available?_

See FAQ H3

_4 What information about protocols should I provide_

Any work done to collect, create, or process material should be described in protocol documents: either the Standard Operating Procedure (SOP) document that you followed plus information about deviations therefore, or, if that does not exist, then you should create your own protocol document by writing down what you did. You can then either publish this as a protocol (e.g. OBPS, protocols.io, zenodo) or provide it as part of your dataset package when you publish your final data.

A protocol document should include the details of every step you followed in collecting, creating, and/or processing the material, such that someone else can follow that.   

_5. How can I provide provenance information_

For data that you publish, a certain among of provenance information can be added to the metadata of that publisher: often the who, what (taxonomy, parameters), when are described in metadata, and sometimes you can also include links to the protocols. However, on the whole most data publishers do not accommodate well for the provision of provenance. So instead you can describe this in a file, in which you include all the provenance information 
- Who did the work, who owns the data, the licence, your desired citation 
- How was the work done (protocols and and software parameter files -- see FAQ G). - 
- Where did the source material/measurements (geocoordinates) or source data (URL) come from
- At what date/time was any source material or measurements made? 
- What is in the dataset (which parameters/measurements, which species, which EOVs/EBVs)

You can contact WP1 for advice about formulating such a provenance file.

# G Software

_1 What information about software do I need to document_

- Software that you create need to be described with their own metadata. There is a particular template for this description provided by the CodeMeta project, and when it is time for you to do this, ask WP1 for the template and guidance. 
- The metadata required will be: details of the contributors, the funders, the maintainers. The software language. The libraries used in the software, including their versions. 
- If you use other software in your work, then you should include metadata about that software as part of the provenance of your eventual products: name of the software, version used, URL of the software (e.g. a GH repository), citation required by the software.
- For all software (your own or other), you need to also provide either the input files you used or a text file listing the input parameters you set. 

_2 How do I publish my software?_

- Publish also any software you create in your work. One way to do this is to put the software on GitHub (making it public), describe the software using a CodeMeta template that katrina.exter@vliz.be can provide for you, and then linking that to Zenodo using the advise on https://coderefinery.github.io/github-without-command-line/doi/

# H Sharing/publishing

_1 What steps do I take when publishing my meta-analysis/data compilation?_

Any data created in MBO will need to be published as a dataset in an archive/repository; this will include any meta-analysis, any gathering of data from various sources to create a new dataset.
The spreadsheets that you collect the metadata and possibly also the metadata will become the dataset that you publish, together with any other explanatory text files or spreadsheets (see FAQ A3). 

Step 1: make sure your (data and metadata) spreadsheets are filled in and formatted as explained in FAQ A,B,C,D,E.
Step 2: spreadsheets need to be published as CSV format, not as excel (xlsx) or other proprietary formats. When doing so, pay attention to the advice in FAQ I.
Step 3: decide where you want to publish your data → you can ask WP1 for advice. When we say “publish”, we do not mean a scientific journal, we mean a public database or archive (OBIS, PANGAEA, etc).
Step 4: make sure that your metadata description of that dataset is as complete as that publisher allows. 
Step 5: enter the URL/DOI and other details of that publication on the WP2,3,4 or 5 googlesheet:https://drive.google.com/drive/folders/1L7Kpz75q0rh6hjZdc7365VV1_Yb07jmi.   


_2 What steps do I take when publishing my data as derived from already-published data_

Any data created in MBO will need to be published as a dataset in an archive/repository; this will include data created by you from source data, e.g. by processing through some software, or by having selected/combined subsets, or by having done QC on some source data, etc. 

Where those data are spreadsheets, remember to include a metadata spreadsheet (FAS A3) and possibly an explanatory and provenance (FAQ F5) text file.
 
It will be necessary to describe the provenance of those published datasets. Often this is not fully accommodated in online archives, so you should take the approach of writing this into a text file and publishing that file along with your datasets. See FAQ F. 

Remember also to publish any code created under MBO (see FAQ G1).

_3 What steps do I take when publishing my data (as derived from NOT already-published data)_

If the data that you are using in your analysis are not publicly accessible, i.e. they are not published, then you should publish them yourself, following the advice given in points 1 and 2 above.  
If these data “belong” to another organisation or someone else, you should consult with them in this process. Perhaps they want to publish the data themselves? If they do not allow the data to be published (but your analysis of those data can be published, otherwise they cannot be MBO data), at a minimum there should be a metadata record of that data in a public archive/catalogue, where the data are not included as a download. If this happens, ask WP1 for advice as it will have to be dealt with on a case-by-case basis.

# I Excel/google to CSV
 
_1 What do I have to pay attention to when converting my spreadsheet to CSV_

When you want to publish your data. I.e. make them public, you need to export each tab of your spreadsheet as CSV. When doing that, bear these points in mind:
- Make sure you modify or remove the default formatting of the spreadsheet app (usually excel or google) you are using, as that always messes up numbers and dates. See FAQ C1 and C3 for specific advice. 
- When you do save to CSV format, remember to ensure you are displaying the entire spreadsheet (no filter!) at the time
- And remember that you will need to export each tab one at a time.
- Remember that any colours, comments, or fancy characters you have used will disappear when you export as CSV



**J What other things can we can help you with**

- If you have standard instruments/parameters that you use/collect, we can provide a mapping to vocabularies as this will significantly interoperability not only between the WP5 datasets, but also other (non-Marco Bolo) data (see point 1)
- If you have standardised, published (DOI or PDF) methodologies for your data collection/analysis, please let us know as we can create a repository on GitHub to hold those, and which will allow us to use it as a guide for EOV generation. (see point 17)
