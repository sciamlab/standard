<br />
<div class="panel panel-warning">
    <div class="panel-heading">
       <h4 class="panel-title"> <span class="glyphicon glyphicon-comment"></span>Open for consultation</h4>
     </div>
     <div class="panel-body"><p>This version is open for consultation until July 15th. Visit <a hef="http://ocds.open-contracting.org">http://ocds.open-contracting.org</a> for more background information.</p>
     </div>
</div>

[TOC]

##Purpose

This is the first release of the Open Contracting Data Standard, Data Model. It presents a high-level overview of the structure of the Data Standard based on supply-side research and initial use-case feedback. 

The purpose of this release is to obtain feedback from the Open Contracting community on the Data Model Draft before creating specific specific field names, reference lists, and file formats.

Throughout the document there are a series of questions to help guide the type of feedback we are seeking. We also welcome general feedback.

Over the coming weeks we will continue to iteratively revise the Data Model Draft based on community feedback. One can follow revisions at [Open Contracting Data Standard](https://github.com/open-contracting/standard/commits/master/standard/standard.md)

This document is focused on traditional procurement, later revisions of the standard are planned to include other types of contracting such as Public Private Partnerships, Extractives and Land.

There are three main discussion areas that we hope to stimulate feedback and debate on with this early release:

- What are the core components of a procurement standard
- The idea of balancing the need of data producers & data consumers through releases & a compiled contracting record
- The need for a unique contracting ID

##Background

Countries signing up to the Open Contracting Global Principles commit to share "information related to the formation, performance, and completion of public contracts" including data on all stages of contracting, from planning to performance evaluations, and information on subcontracting arrangements.

The Open Contracting Data Standard is being developed to allow much of this information to be shared as structured data: delivered in ways that enable the widest possible range of users to benefit from greater transparency of contracting arrangements and supporting greater participation, monitoring and oversight in contracting processes.

The Open Contracting Data Standard is a core product of the Open Contracting Partnership. Version 1.0 of the standard is being developed for the OCP by the World Wide Web Foundation and World Bank, through a project supported by The Omidyar Network and the World Bank.

More detailed information about the Development Process is available at the bottom of this document - [Development Process](#development-process)

## Sources
The development of the Data Model Draft has been based on:

* **Assessing data currently supplied through contract portals** - in order to understand the data that governments currently hold and publish, and how it is structured. To carry out this analysis we created the [Contracting Data Comparison tool](http://ocds.open-contracting.org/opendatacomparison/), and [Contracting Data Map](http://ocds.open-contracting.org/opendatacomparison/datamap/) which explores the fields of data available from a wide range of different government contracting data portals around the world. 
* **Exploring demand for data on contracting** - to identify the ways in which different users think about contracting data, and how they want to use it. This work is ongoing, and only initial use cases are factored into this conceptual model. In the next iteration of the conceptual model and field level information, further emphasis will be placed on use cases. 

This initial iteration of the conceptual model is focussed on procurement processes. Future iterations will look at contracts in the land and extractives sector, and we anticipate this will lead to further developments in the terminology used. 

We offer this draft data model as the basis for a discussion. Following feedback over June and July 2014 we will revise or confirm the conceptual model, and will work towards providing more detailed field-level information by the third quarter of 2014.

##Conceptual Model

### The contracting process 

The contracting process is the sequence of events related to the lifespan of a contract, beginning with planning and culminating in contract closure. 

![Visual of opencontrating process](https://raw.githubusercontent.com/open-contracting/standard/master/standard/assets/contracting%20process.png)

<p>* Formation, when dealing with basic procurement processes, will often be referred to as Tendering & Award.</p>

For descriptions of the phases see the "Definitions" tab at the top.

### Conceptual Model
We propose an Open Contracting Data Standard consisting of two parts:

- A **contracting record** - is used to summarize all the key
  features of the a unique contracting process, bringing together information from 
  all phases of the contracting process into one record. It is updated as 
  new information becomes available to accurately reflect the current state of the 
  contract processes. The contracting record should provide an 
  at-a-glance view of key information and can then be used to access more detailed information from the releases.

- A set of **contracting releases** - specific releases of information, 
  such as tender notices, award notices, or details of a contract. 
  The revision history of releases should be kept, and releases will often 
  have a number of attached documents. The contracting releases provide 
  in-depth information about a particular aspect of the contracting process, 
  and should be published in a timely fashion.  

The information in contracting **releases** is used to build a contracting 
**record** - each contracting release must, therefore, be tied to a unique 
**open contracting identifier**. See later section on identifying a unique 
contracting process.

![Visual of publishing process](https://raw.githubusercontent.com/open-contracting/standard/master/standard/assets/releases%20and%20record.png)

##The contracting record 
The contracting record is a master document that collects together a summary of key information about a contracting process. 

Each contracting record represents a single contracting process and should be uniquely identifiable.

The contracting record will be possible to serialize in a flat/table form with as little information loss as possible. 

The contracting record will contains the latest version of the information for each of the core components, as well as information about 
the publishing source, the last updated information, and crucially, links to all releases associated with this contracting process.

The core components of the Contracting Record and our data model are:

-   Buyer
    -   The buyer is the department, agency or entity who is paying for
        the goods /services in the contract. The buyer may be distinct
        from a procuring agency or awarding body - an independent entity
        that runs the procurement process (tender and award) - this
        allows for pooling of resources as well as enhancing
        impartiality).
-   Supplier
    -   The supplier is the entity, or entities, providing the goods or services in
        the contract. It could be an individual, a private organization,
        or another public body.
-   Items - Goods / services / works
    -   Details, ideally at the line item level, of the goods,
        services or works being procured. This should include a standardized code (detailing 
        the items category e.g. construction or agricultural goods)
        & description as well as any supporting information or documents, such as technical specifications. This category will be expanded later
        as we move to support other types of contract beyond procurement.
-   Planning
    -   Before a tender notice is issued, there is a procurement plan in place, an intent to procure. 
        Also known as Prior Information or a Forward Procurement Schedule. This category contains information specific to planning for this
        specific contracting process. For example, the confidence that the procurement will take place. (The planning release may contain information about other components, such as the buyer, and items for procurement).
-   Formation process
    -   In the case of standard procurement, this the information about the tender process. It may include:
        opening dates, closing dates, consultation information, the type
        of bidding process (open process, selective tendering, limited
        tendering or sole source), award criteria (lowest cost, best
        proposal, appropriate quality), as well as links to supporting
        documentation, a tender ID, and a link to the tender notice. It may
        also include information such as the number of bids and bidders who
        participated in the process.
-   Award details
    -   This is information about the Contract Award e.g. the award date, and the
        awarded value. This is distinct from the contract information which reflects the
        actual contract document which is finalized and signed after an award. In the case
        of framework contracts, where multiple contracts are issued in a contracting process, the
        award would contain the details of the framework award.
-   Contract
    -   Information about the contract document(s) itself.
        Including award signature date, start & end date, 
        links to the award & contract documents, and termination information. 
        It would also capture details of contract amendments (change of value, deliverables
        alterations, no-cost extensions)
-   Performance
    -   In performance we store details related to the contract implementation
        including details of payments made, evaluation, audit and performance reports.

The contracting record will reflect the latest state of the contracting process. 
For example, if a tender is issued for Widget A with a minimum value of $10 
and maximum of $20, at the tender stage the 'Amounts:minimum' would be $10, 
and 'Amounts:maximum' would be $20. If during consulation the range is 
determined to be unrealistic and a tender ammendment is issued changing the 
range of acceptable tenders to $20 - $30 then the contracting record would be 
updated to an 'Amounts:minimum' of $20 and 'Amounts:maximum' of $30. 
To see the history of these amounts would require looking at the individual 
contracting releases or tracking changes to the contracting record. 

<div class="panel panel-success">
    <div class="panel-heading">
       <h4 class="panel-title"> <span class="glyphicon glyphicon-question-sign"></span> Consultation questions</h4>
     </div>
     <div class="panel-body">
         <ul>
             <li>Does the proposed conceptual model make sense for the ways you want to publish or use open contracting data?</li>
             <li>Which do you need most: a summary contracting record, or detailed releases of information at each stage of the contracting process?</li>
             <li>Do these components cover all the relevant information you want to publish or access about contracting?</li>
             <li>How does the proposed approach of having the contracting record represent the latest stage of contracting (i.e. overwriting earlier data) affect how you might publish or use open contracting data?</li>
             <li>This model necessitates a unique contracting ID across the entire contracting process. What are the challenges around this?</li>
         </ul>     
     </div>
</div>

## Contracting releases
The contracting record is formed and updated through releases. Releases are
snapshots of information which may be the first time information has been 
released or they may be revisions or amendments. Examples of release types are:

### Release tracking 
Ideally, each release will refer to the unique open contracting process id, 
and the contracting record will be updated with a link to each
notice and amendment, thereby providing a two-way data link.

In the event that the publisher is not maintaining a contract record,
the ID of the first notice will serve as the unique identifier moving
forward the contracting process. Subsequent notices and amendments may
have their own unique identifiers (e.g. an award notice identifier) but
they must all contain a reference to the unique identifier.

Each release, or a group of releases, will contain publisher
information, and each release will contain a release number and date
from that publisher. The idea is to accommodate the modularization of
publishing such that along the contracting process, different bodies
could publish different sets of releases. For example, one publisher
for tenders and awards, and a separate publisher for contracts
releases. In addition, third-party publishers may wish to augment the
contracting data with their own releases such as an Add On containing
geo-coding information.

<div class="panel panel-success">
    <div class="panel-heading">
       <h4 class="panel-title"> <span class="glyphicon glyphicon-question-sign"></span> Consultation questions</h4>
     </div>
     <div class="panel-body">
         In future research we will be investigating different ways that amendments and updates to releases might be represented.
         <ul>
             <li>What are options / approaches, from a technical / data structure point of view to represent and publish amendments to releases? And what are the strengths and weaknesses?</li>
         </ul>     
     </div>
</div>

### Defining a unique contracting process
For the data standard, defining a unique contracting process is critical for getting useful, comparable, clean data. But, there are cases 
where what the unique process is not obvious. For example, a framework contract has only one tender and award but many contracts associated with that award.

We define a unique contracting process as that with a unique tendering / competitive phase.

**Example 1**

<div class="pull-left"><img alt="Multiple processes" src="https://raw.githubusercontent.com/open-contracting/standard/master/standard/assets/tender_notice_with_multiple_journeys.png"></div>

This Tender notice has a single ID and six line items. However, to secure each item suppliers must enter a seperate bid and the competition is handled seperately for each item leading to 6 contracts. Because the competitive process is unique for each 6 items there are 6 contracting processes here, in spite of the single Tender Notice ID.

<div class="clearfix"></div>

**Example 2**
<div class="pull-left"><img alt="Single process" src="https://raw.githubusercontent.com/open-contracting/standard/master/standard/assets/one_journey_multiple_contracts.png"></div>

This snippet from a [tender notice](https://buyandsell.gc.ca/procurement-data/tender-notice/PW-14-00635129) offers an unspecified number of contracts for the successful supplier(s). The details note that there is a limit of $25k per contract, anything higher than that must be rebid competitively. All of the $25k or less contracts that are awarded under the award that will result from this tender are part of a single contracting process, because of the single bidding process.

<div class="clearfix"></div>

### Add on information
In addition to the core components, there will be cases where
publishers, or users, need to augment the core data with their
own information. The standard will provide a mechanism for Add-On
information. This will include additional fields in core components as
well as Add On components (e.g. new kinds of **contracting release**).

The publishing and re-use of add-ons will be encouraged to try and
reduce duplication and facilitate reuse of tools. The use of Add-Ons
will be subject to the following restrictions[^2]:

-   It must not use terms from outside this specification's terms where
    this specification's terms would suffice

-   It may use terms from outside this specification's terms where this
    specification's terms are insufficient.

[^2]:
    The use of add-on conditions were adapted from the
    The Popolo Project - [http://popoloproject.com/specs/\#conformance](http://popoloproject.com/specs/#conformance)

### A note on framework contracts
Many public procurements take place under framework agreements, or standing arrangements. These help facilitate routine purchasing. Suppliers are pre-approved to provide a list of goods or services. Under a framework agreement, there are typically multiple contracts that are all authorized by a single award. In the data standard, an award notice release would define the framework
and this information would be stored in the contracting record under Award details. Then there will be multiple contract signature releases and each one would create a new Contract section in the contracting record. This provides a way to aggregate all the information on the contracts given under a single framework agreement.

### Linking to documents
There are often many documents associated with a contracting process including tender specifications, contract documents, performance reports etc. The standard will
provide a way to link to these documents. We are considering how to handle documents in the contracting record. We
 may have a simplified contracting record that indicates that documents are available and a full contracting record that provides links to all
the available documents. As we flesh out the different serializations over July and August this will be defined. Document links will always 
be available through the release that declared them.

## Use Cases 
This draft is based primarily on research of existing published datasets as well as preliminary work on use cases for data demand. In particular, we are seeking to support the following demands on the data:

- achieve value for money
- to detect corruption
- to compete for public contracts
- to monitor service delivery
    
<div class="panel panel-success">
    <div class="panel-heading">
       <h4 class="panel-title"> <span class="glyphicon glyphicon-question-sign"></span> Consultation questions</h4>
     </div>
     <div class="panel-body">
         <ul>
             <li>In your opinion, does the proposed conceptual model work for these use cases?</li>
             <li>Are there other important use cases we should be considering? </li>
             <li>Are there use cases you can envisage where the proposed conceptual model does not work well? </li>
         </ul>     
     </div>
</div>

## Development process

The development of the Data Model has been based on:

### 1) Supply-side research 

The supply-side research is focused on comparing contract data (37 datasets with over 175 downloadable assets from 27 publishers, from across the world). 26 publishers are from 15 countries that were selected as priority countries due to their current activity in open government and the Open Government Partnership (OGP) Action Plan. The effort sought to understand:

* which elements of the contracting process are captured in currently published data;
* which fields are commonly found across different datasets;
* how do different datasets represent and model the contracting process; and
* how far are there common identifiers that can be used to link datasets.
    
To answer the above questions a Contracting Data Comparison tool was created with a team of volunteer developers to provide a platform for curating meta-data about public contracting datasets from the priority countries. 

The effort focused on capturing the metadata of contract data available. As it develops, the intention is for the Contracting Data Comparison tool to allow for wider public participation and thus create an ever more detailed picture of the landscape of contracting data availability and focus. 
  
### 2) Demand-side use-cases

This draft is based primarily on research of existing published datasets. At the same time, the project has begun to explore priority use cases for open contracting data through workshops, webinars, a mailing list, and bilateral discussions with more than 200 stakeholders. The purpose of demand-side research is to capture the real needs and circumstances of the publishers and users of public contracting data. 

In our consultations with government, civil society, donors, journalists, auditors, and the private sector, four primary use cases emerged. These users are interested to use open contracting data in order to:

* Achieve value for money for the procuring entity;
* Enable the private sector to compete for public contracts;
* Monitor service delivery for effectiveness; and
* Detect corruption and fraud in public contracting.

The draft use cases are being developed on an ongoing basis and can be found [here](https://docs.google.com/document/d/1zdgqSf-LUFVxO6Y_7v1cQf7l0vx35-p502jAI49JRmQ/edit?usp=sharing). These use cases not only demonstrate what can and could be done with open contracting data, but will also shape the development of the Open Contracting Data Standard as we move towards defining the field-level specification.

### 3) Research on related initiatives 

There are existing standardization efforts for budget and spending data under development through the Open Spending Project. In line with the principles of [Joined Up Data](http://devinit.org/report/joined-data-building-blocks-common-standards/) this project will explore ways to connect data in the Open Contracting Data Standard with data in the proposed Open Spending and Open Budget Data Standards, among others.

In addition, the approach taken is informed by the development of other data standards. Research related to the Data Standard Architecture and Data Standard Governance will be released separately from the Data Model Draft.

##Next steps
Over June 2014 we will be validating the conceptual model proposed in this document of a Contracing Process, Contracting Records and Contracting Releases. 
You are invited to add your comments directly to the online copy of this document at [http://ocds.open-contracting.org/standard/](http://ocds.open-contracting.org/standard/), 
or to join discussions on [the project mailing list](https://groups.google.com/a/webfoundation.org/forum/#!forum/public-ocds). 

Over July and August 2014 we will be fleshing out in more detail the data fields that belong to each of the core components, and will develop a full data model. The proposed model will be validated against a range of use cases developed through demand side research. 

This Data Model Draft will be format-agnostic. That is, it will be a generic model rather than a specific serialization in JSON, XML or CSV. 

Following the development and validation of the model, we will outline a number of approaches to serialize this data in different priority formats. 

Throughout this process we will be seeking to re-use existing data structures from prior standards. 

## Schema re-use 
This document is intended as a non-technical introduction to the
standard, and as a such does not include an ontology (the formal data
representation of the standard). However, its worth noting here that we
will be reusing existing specifications wherever appropriate. In
particular, we already know that Buyer and Supplier are types of
Organization, that will have People and Addresses. There are already
well-known schemas for Organizations, People and Addresses and so we
will re-use this existing standard work where possible.

There is an [existing standardisation effort](http://community.openspending.org/research/standard/) 
for Budget and Spending data under development through the Open Spending project. In line with the principles of Joined Up 
Data we will explore ways to connect data in the Open Contracting Data Standard with data in the proposed Open Spending and 
Open Budget data standards. 

<div class="panel panel-success">
    <div class="panel-heading">
       <h4 class="panel-title"> <span class="glyphicon glyphicon-question-sign"></span> Consultation questions</h4>
     </div>
     <div class="panel-body">
         <ul>
             <li>Are there other standards we should looking to 'join up' to in order to supply tracing the full contracting process, beyond those aspects that will be captured in the Open Contracting Data Standard?</li>
         </ul>     
     </div>
</div>


##Acknowledgements

The Open Contracting Data Standard is a core product of the [Open Contracting Partnership (OCP)](http://www.open-contracting.org/). Version 1.0 of the standard is being developed for the OCP by the [World Wide Web Foundation](http://www.webfoundation.org), through a project supported by The [Omidyar Network](http://www.omidyar.com/) and the [World Bank](http://www.worldbank.org)".

This document contains significant contributions from Sarah Bird ([Aptivate](http://www.aptivate.org)), Ana Brandusescu and Tim Davies (World Wide Web Foundation). Other contributors include: Jose M. Alonso (World Wide Web Foundation), Steven Davenport (World Bank), Lindsey Marchessault, Michael Roberts (World Wide Web Foundation), and Marcela Rozo (World Bank). 

