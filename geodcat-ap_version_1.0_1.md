Version 1.0

# Document Metadata

|            |                                                                                                                                |
|------------|--------------------------------------------------------------------------------------------------------------------------------|
| Date       | 2015-12-23                                                                                                                     |
| Status     | Final (amended: 2016-04-08)                                                                                                    |
| Version    | 1.0                                                                                                                            |
| Access URL | <https://joinup.ec.europa.eu/node/148281>                                                                                      |
| Rights     | © 2015 European Union                                                                                                          |
| Licence    | ISA Open Metadata Licence v1.1, retrievable from <https://joinup.ec.europa.eu/category/licence/isa-open-metadata-licence-v11>. |

**Disclaimer:**

This specification was prepared for the ISA Programme by: PwC EU Services.

The views expressed in this specification are purely those of the authors and may not, in any circumstances, be interpreted as stating an official position of the European Commission.

The European Commission does not guarantee the accuracy of the information included in this study, nor does it accept any responsibility for any use thereof.

Reference herein to any specific products, specifications, process, or service by trade name, trademark, manufacturer, or otherwise, does not necessarily constitute or imply its endorsement, recommendation, or favouring by the European Commission.

All care has been taken by the author to ensure that s/he has obtained, where necessary, permission to use any parts of manuscripts including illustrations, maps, and graphs, on which intellectual property rights already exist from the titular holder(s) of such rights or from her/his or their legal representative.

**Note on this document (2016-04-08)**

This version of the GeoDCAT-AP 1.0 has been amended with respect to the original one in order to correct a typo concerning the URIs of the code lists of the INSPIRE Registry.

No other changes have been done on the original specification

# Contents

## Table of contents

[1 Introduction 7](#_Toc447881017)

[1.1 Objectives 7](#_Toc447881018)

[1.2 Structure of this document 8](#_Toc447881019)

[2 Related standards and work 9](#_Toc447881020)

[2.1 ISO 19115:2003, ISO 19139 and ISO 19115-1:2014 9](#_Toc447881021)

[2.2 OGC Catalog Service for the Web 9](#_Toc447881022)

[2.3 INSPIRE Metadata Regulation and INSPIRE Metadata Technical Guidelines 9](#_Toc447881023)

[2.4 DCAT and DCAT-AP 10](#_Toc447881024)

[2.5 Alignment of INSPIRE metadata with Dublin Core 10](#_Toc447881025)

[2.6 Alignment of INSPIRE metadata with DCAT-AP 10](#_Toc447881026)

[2.7 Alignment of EuroVoc – GEMET – INSPIRE themes 11](#_Toc447881027)

[2.8 GeoDCAT-AP XSLT script and API 11](#_Toc447881028)

[3 Motivation and use cases 12](#motivation-and-use-cases)

[4 Methodology and summary of results 13](#_Toc447881030)

[4.1 Alignment criteria and requirements 13](#alignment-criteria-and-requirements)

[4.2 Metadata elements to be covered by GeoDCAT-AP 13](#_Toc447881032)

[4.3 Alignments defined in GeoDCAT-AP 14](#_Toc447881033)

[5 RDF syntax bindings for INSPIRE and ISO 19115 metadata elements 16](#_Toc447881034)

[5.1 Used namespaces 16](#_Toc447881035)

[5.2 Overview of bindings for GeoDCAT-AP Core 18](#overview-of-bindings-for-geodcat-ap-core)

[5.3 Overview of bindings for GeoDCAT-AP Extended 23](#overview-of-bindings-for-geodcat-ap-extended)

[6 Controlled vocabularies 27](#_Toc447881038)

[Acknowledgements 31](#_Toc447881039)

[References 35](#references)

[Annex I Overview of metadata elements covered by GeoDCAT-AP 39](#_Toc447881041)

[Annex II Detailed usage notes and examples 42](#_Toc447881042)

[II.1 Resource title - \*Dataset title 42](#_Toc447881043)

[II.2 Resource abstract - \*Abstract describing the dataset 42](#_Toc447881044)

[II.3 Resource type - \*not in ISO 19115 core 43](#_Toc447881045)

[II.4 Resource locator - \*On-line resource 45](#_Toc447881046)

[II.5 Unique resource identifier - \*not in ISO 19115 core 47](#_Toc447881047)

[II.6 Coupled resource - \*not in ISO 19115 core 49](#_Toc447881048)

[II.7 Resource language and metadata language - \*Dataset language and Metadata language 50](#_Toc447881049)

[II.8 Topic category, originating controlled vocabulary, and keyword value - \*Dataset topic category 51](#_Toc447881050)

[II.8.1 Topic category and keyword in datasets and dataset series 52](#topic-category-and-keyword-in-datasets-and-dataset-series)

[II.8.2 Keyword in services 53](#_Toc447881052)

[II.9 Spatial data service type - \*not in ISO 19115 core 57](#_Toc447881053)

[II.10 Geographic bounding box - \*Geographic location of the dataset (by 4 coordinates or by geographic identifier) 57](#_Toc447881054)

[II.11 Temporal reference and metadata date –\*Additional extent information for the dataset (vertical and temporal) and \*Metadata date stamp 59](#_Toc447881055)

[II.12 Lineage - \*Lineage 61](#_Toc447881056)

[II.13 Spatial resolution – Spatial resolution of the dataset 62](#_Toc447881057)

[II.14 Conformity and data quality - \*not in ISO 19115 core 63](#_Toc447881058)

[II.15 Conditions for access and use and limitations on public access – Use limitation and access / other constraints 65](#_Toc447881059)

[II.16 Responsible party and metadata point of contact - \*Dataset responsible party and \*Metadata point of contact 66](#_Toc447881060)

[II.17 \*Metadata file identifier 70](#_Toc447881061)

[II.18 \*Metadata standard name, \*Metadata standard version 70](#_Toc447881062)

[II.19 \*Metadata characterset 72](#_Toc447881063)

[II.20 Metadata point of contact - \*Metadata point of contact 72](#_Toc447881064)

[II.21 Metadata date - \*Metadata date stamp 72](#_Toc447881065)

[II.22 Metadata language - \*Metadata language 72](#_Toc447881066)

[II.23 Coordinate reference systems and Temporal reference systems – \*Reference System 72](#_Toc447881067)

[II.24 Character encoding - \*Dataset character set and \*Metadata character set 74](#_Toc447881068)

[II.25 Encoding - \*Distribution format 77](#_Toc447881069)

[II.26 Spatial representation type – \*Spatial representation type 78](#_Toc447881070)

[II.27 Maintenance information - \*not in ISO 19115 core 79](#_Toc447881071)

[Annex III Comparison between INSPIRE and ISO 19115-1:2014 81](#_Toc447881072)

[III.1 Spatial dataset and spatial dataset series 81](#_Toc447881073)

[III.2 Services 84](#_Toc447881074)

## List of tables

[Table 1: Namespace prefixes 16](#_Toc447881075)

[Table 2: Element bindings for GeoDCAT-AP Core 18](#_Toc447881076)

[Table 3: Element bindings for GeoDCAT-AP Extended 23](#_Toc447881077)

[Table 4: Controlled vocabularies to be used 27](#_Toc447881078)

[Table 5: Overview of covered metadata elements 39](#_Toc447881079)

[Table 6: Mappings for metadata element ‘originating controlled vocabulary’ 53](#_Toc447881080)

[Table 7: Mappings for metadata element ‘conformity’ 63](#_Toc447881081)

[Table 8: Mappings for metadata element ‘responsible party’ 67](#_Toc447881082)

[Table 9: Responsible party roles 67](#_Toc447881083)

[Table 10: Metadata standard name and metadata standard version 71](#_Toc447881084)

[Table 11: Metadata elements used for discovery of geographic datasets and series 81](#_Toc447881085)

[Table 12: Metadata elements used for discovery of service resources 84](#_Toc447881086)

## Abbreviations used in this document

|            |                                                                  |
|------------|------------------------------------------------------------------|
| ARE3NA     | Reusable INSPIRE Reference Platform                              |
| CRS        | Coordinate Reference System                                      |
| CSW        | Catalog Services for the Web                                     |
| DCAT       | Data Catalog Vocabulary                                          |
| DCAT-AP    | DCAT Application Profile for Data Portals in Europe              |
| DCMI       | Dublin Core Metadata Initiative                                  |
| EARL       | Evaluation and Report Language                                   |
| EU         | European Union                                                   |
| EuroVoc    | Multilingual Thesaurus of the European Union                     |
| GEMET      | GEneral Multilingual Environmental Thesaurus                     |
| GML        | Geography Markup Language                                        |
| GeoDCAT-AP | Geographical extension of DCAT-AP                                |
| IANA       | Internet Assigned Numbers Authority                              |
| INSPIRE    | Infrastructure for Spatial Information in the European Community |
| ISO        | International Standardisation Organisation                       |
| JRC        | European Commission - Joint Research Centre                      |
| MDR        | Metadata Registry                                                |
| NAL        | Named Authority Lists                                            |
| OGC        | Open Geospatial Consortium                                       |
| RDF        | Resource Description Framework                                   |
| RFC        | Request for Comments                                             |
| SPARQL     | SPARQL Protocol and RDF Query                                    |
| URI        | Uniform Resource Identifier                                      |
| W3C        | World Wide Web Consortium                                        |
| WG         | Working Group                                                    |
| WKT        | Well Known Text                                                  |
| XML        | eXtensible Markup Language                                       |
| XSLT       | eXtensible Stylesheet Language Transformations                   |

 <span id="_Toc414637463" class="anchor"><span id="_Toc447881017" class="anchor"></span></span>Introduction
===========================================================================================================

This document contains the specification for GeoDCAT-AP, an extension of the DCAT application profile for data portals in Europe (DCAT-AP) \[DCAT-AP\] for describing geospatial datasets, dataset series, and services.

Its basic use case is to make spatial datasets, dataset series, and services searchable on general data portals, thereby making geospatial information better searchable across borders and sectors. This can be achieved by the exchange of descriptions of data sets among data portals. GeoDCAT-AP provides an RDF syntax binding for the union of metadata elements of the core profile of ISO 19115:2003 \[ISO19115\] and those defined in the framework of the INSPIRE Directive \[INSPIRE-DIR\].

**The GeoDCAT-AP specification does not replace the INSPIRE Metadata Regulation** \[INSPIRE-MD-REG\] **nor the INSPIRE Metadata technical guidelines** \[INSPIRE-MD-TG\] **based on ISO 19115 and ISO 19119.** Its purpose is to give owners of geospatial metadata the possibility to achieve more by providing the means of an *additional* implementation through harmonised RDF syntax bindings. Conversion rules to RDF syntax would allow Member States to maintain their collections of INSPIRE-relevant datasets following the INSPIRE Metadata technical guidelines based on ISO 19115 and ISO 19119 \[ISO19119\], while at the same time publishing these collections on DCAT-AP-conformant data portals. A conversion to RDF syntax allows additional metadata elements to be displayed on general-purposed data portals, provided that such data portals are capable of displaying additional metadata elements. Additionally, data portals may be capable of providing machine-to-machine interfaces where additional metadata could be provided.

<span id="_Toc414637464" class="anchor"><span id="_Ref422243932" class="anchor"><span id="_Toc447881018" class="anchor"></span></span></span>Objectives
-------------------------------------------------------------------------------------------------------------------------------------------------------

The objective of this work is to define an *RDF syntax* that can be used for the exchange of descriptions of *spatial* datasets, dataset series, and services among data portals. The RDF syntax should extend the DCAT Application Profile for data portals in Europe \[DCAT-AP\].

-   To provide an RDF syntax binding for the *union* of the elements in the INSPIRE metadata schema and the core profile of ISO 19115:2003. The guiding design principle is to make the resulting RDF syntax as simple as possible; thereby maximally using existing RDF vocabularies – such as the Dublin Core and DCAT-AP –, and as much as possible avoiding minting new terms. The defined syntax binding must enable the conversion of metadata records *from* ISO 19115 / INSPIRE *to* a harmonised RDF representation. The ability to convert metadata records from RDF to ISO 19115 / INSPIRE is not a requirement.

-   To formulate recommendations to the Working Group dealing with the revision of the DCAT-AP, to maximally align DCAT-AP and GeoDCAT-AP.

-   To take into account and refer to alignment of relevant controlled vocabularies (e.g., the alignments between GEMET, INSPIRE themes, EuroVoc carried out by the Publications Office of the EU[1]).

Additionally, the following outcomes may be achieved, outside the context of this specification:

-   To define new controlled vocabularies or define mappings between controlled vocabularies;

-   To design executable transformation rules (i.e., an XSLT script \[GEODCAT-XSLT\]), as a reference implementation of the mappings defined in the GeoDCAT-AP specification.

-   To define an RDF syntax binding for the elements in ISO 19115-1:2014.

    1.  <span id="_Toc414637465" class="anchor"><span id="_Toc447881019" class="anchor"></span></span>Structure of this document
        ------------------------------------------------------------------------------------------------------------------------

This document consists of the following sections:

-   Section 1 introduces this document;

-   Section 2 provides an overview of related work;

-   Section 3 provides the use cases that motivate the creation of a GeoDCAT-AP specification;

-   Section 4 provides a description of the methodology used in terms of alignment of criteria and requirement, metadata elements covered by GeoDCAT-AP, and a summary of the results;

-   Section 5 provides the suggested RDF syntax bindings for metadata elements;

-   Section 6 provides an overview of controlled vocabularies with relevant URI sets;

This specification is accompanied by a set of annexes, providing additional reference and support material. More precisely:

-   Annex I provides a summary of the INSPIRE and ISO 19115 elements covered by GeoDCAT-AP;

-   Annex II provides detailed usage notes and examples for each of the metadata elements covered by GeoDCAT-AP;

-   Annex III carries out a comparison of INSPIRE metadata with ISO 19115-1:2014.

<span id="_Ref412533889" class="anchor"><span id="_Toc414637466" class="anchor"><span id="_Toc447881020" class="anchor"></span></span></span>Related standards and work
=======================================================================================================================================================================

This section contains an overview of related standards and work.

<span id="_Toc414637467" class="anchor"><span id="_Toc447881021" class="anchor"><span id="_Ref355964706" class="anchor"><span id="_Toc387936586" class="anchor"></span></span></span></span>ISO 19115:2003, ISO 19139 and ISO 19115-1:2014
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

ISO 19115:2003 \[ISO19115\], a standard of the International Organization for Standardization (ISO), defines how to describe geographical information. ISO 19139 \[ISO19139\] defines the XML-based implementation for ISO 19115.

ISO 19115-1:2014 \[ISO19115-1\] has superseded ISO 19115:2003. At the date of publication of this document, the XML-based implementation of ISO 19115-1:2014 (namely, ISO 19115-3), was finalised but not yet officially released. Annex III contains an overview of the most important changes.

As documented in the INSPIRE Metadata Technical Guidelines \[INSPIRE-MD-TG\], the conformance of a metadata set to the core profile of ISO 19115 does not guarantee conformance to the INSPIRE metadata specifications, although there is a large correspondence.

<span id="_Toc414637470" class="anchor"><span id="_Toc447881022" class="anchor"></span></span>OGC Catalog Service for the Web
-----------------------------------------------------------------------------------------------------------------------------

Catalog Service for the Web (CSW) \[CSW\] is a standard of the Open Geospatial Consortium (OGC) for exposing a catalogue of geospatial records on the Web. It specifies *the interfaces, bindings, and a framework for defining application profiles required to publish and access digital catalogues of metadata for geospatial data, services, and related resource information. *

> A profile of CSW is used in the INSPIRE Technical Guidance on Discovery Services \[INSPIRE-DS-TG\].

<span id="_Toc414637471" class="anchor"><span id="_Toc447881023" class="anchor"></span></span>INSPIRE Metadata Regulation and INSPIRE Metadata Technical Guidelines
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

The INSPIRE Metadata Technical Guidelines \[INSPIRE-MD-TG\] include rules for the description of resources based on ISO 19115 (datasets and series) and ISO 19119 (services), and by using their XML-based implementation defined in ISO 19139.

INSPIRE[2] \[INSPIRE-DIR\] is a Directive of the European Parliament and of the Council aiming to establish a EU-wide spatial data infrastructure to give cross-border access to information that can be used to support EU environmental policies, as well as other policies or activities having an impact on the environment. The actual scope of this information corresponds to 34 environmental themes, covering also areas having cross-sector relevance – e.g., addresses, buildings, population distribution and demography.

In order to ensure cross-border interoperability of data infrastructures operated by EU Member States, INSPIRE sets out a framework based on common specifications for metadata, data, network services, data and service sharing, monitoring and reporting. Such specifications consist of a set of implementing rules (which take the form of Commission Regulations, i.e., they are legally binding in the EU Member States), along with the corresponding technical guidelines, defined by a regulatory committee composed of representatives of both EU Member States and European Union bodies and institutions.

<span id="_Toc414637472" class="anchor"><span id="_Toc447881024" class="anchor"></span></span>DCAT and DCAT-AP
--------------------------------------------------------------------------------------------------------------

The DCAT Application profile for data portals in Europe (DCAT-AP) \[DCAT-AP\] is a specification based on the W3C’s Data Catalogue vocabulary (DCAT) \[DCAT\] for describing public sector datasets in Europe. Its basic use case is to enable cross-data portal search for data sets and make public sector data better searchable across borders and sectors. This can be achieved by the exchange of descriptions of datasets among data portals.

The application profile is a specification for metadata records to meet the specific application needs of data portals in Europe, while providing semantic interoperability with other applications on the basis of reuse of established controlled vocabularies (e.g. EuroVoc) and mappings to existing metadata vocabularies (e.g., Dublin Core, SDMX, INSPIRE metadata, etc.).

<span id="_Toc414637473" class="anchor"><span id="_Toc447881025" class="anchor"></span></span>Alignment of INSPIRE metadata with Dublin Core
--------------------------------------------------------------------------------------------------------------------------------------------

In 2008, JRC published a report \[INSPIRE-DC\] on the progress made in defining the proper way of expressing elements of INSPIRE metadata in conformance with ISO 15836 (Dublin Core).

<span id="_Toc414637474" class="anchor"><span id="_Toc447881026" class="anchor"></span></span>Alignment of INSPIRE metadata with DCAT-AP
----------------------------------------------------------------------------------------------------------------------------------------

The GeoDCAT-AP specification builds upon prior work conducted by the European Commission’s Joint Research Centre in 2014. This work consisted of an alignment exercise between INSPIRE metadata and DCAT-AP (version 1.0) in the framework of ISA Action 1.17 \[INSPIRE-DCAT\]. The results of this alignment exercise, referred to as INSPIRE+DCAT-AP, are divided in two parts:

-   A Core version which defines alignments for the *subset* of INSPIRE metadata elements supported by DCAT-AP.

-   An Extended version which defines alignments for *all* the INSPIRE metadata elements using DCAT-AP and other vocabularies whenever DCAT-AP is not relevant.

However, INSPIRE+DCAT-AP did not define alignments for the following elements:

-   Some of the metadata elements in the core profile of ISO 19115 – i.e., those related to the metadata character set, metadata identifier and metadata standard. *The GeoDCAT-AP Extended profile– in this document – does provide an RDF syntax binding for these metadata elements.*

-   The INSPIRE metadata elements recommended in the data specifications technical guidelines, summarised in Appendix B.2 to INSPIRE Metadata Technical Guidelines (version 1.3) \[INSPIRE-MD-TG\]. *The GeoDCAT-AP Extended profile– in this document –provides a partial syntax binding for data quality (limited to conformity) and maintenance information (limited to maintenance and update frequency).*

    1.  <span id="_Toc414637475" class="anchor"><span id="_Toc447881027" class="anchor"></span></span>Alignment of EuroVoc – GEMET – INSPIRE themes
        -------------------------------------------------------------------------------------------------------------------------------------------

EuroVoc is a multilingual, multidisciplinary thesaurus covering the activities of the EU, and it is one of the controlled vocabularies recommended in DCAT-AP.

The Publications Office of the EU has defined and published alignments between EuroVoc and other vocabularies, including those typically used in geospatial metadata – in particular, AGROVOC, GEMET, the INSPIRE themes and the INSPIRE feature concept dictionary. It is worth noting that the use of the INSPIRE themes is a legal obligation in INSPIRE metadata.

These alignments are available from the Metadata Registry of the EU Publications Office:

<http://publications.europa.eu/mdr/eurovoc/>

<span id="_Toc437279245" class="anchor"><span id="_Toc437508931" class="anchor"><span id="_Toc437955615" class="anchor"><span id="_Toc437279246" class="anchor"><span id="_Toc437508932" class="anchor"><span id="_Toc437955616" class="anchor"><span id="_Toc447881028" class="anchor"></span></span></span></span></span></span></span>GeoDCAT-AP XSLT script and API
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In the context of ISA Action 1.17 (ARE3NA – Reusable INSPIRE Reference Platform) an XSLT script \[GEODCAT-XSLT\] was created, that can be used to transform ISO 19139 metadata into Geo/DCAT-AP. This XSLT is maintained on the Commission’s Git repository:

<https://webgate.ec.europa.eu/CITnet/stash/projects/ODCKAN/repos/iso-19139-to-dcat-ap/>

The XSLT is complemented with documentation summarising how the GeoDCAT-AP specification has been implemented. This documentation includes:

-   A summary of the mappings, accompanied with detailed examples for some metadata elements.[3]

-   Where the XSLT expects to find HTTP URIs, and how they are used.[4]

<span id="_Toc414637477" class="anchor"><span id="_Ref415092887" class="anchor"><span id="_Ref422243019" class="anchor"></span></span></span>An experimental API has been also developed, as a proof-of-concept for the CSW-based implementation of GeoDCAT-AP. The API uses the GeoDCAT-AP XSLT to transform ISO 19139 records into Geo/DCAT-AP. It supports HTTP content negotiation and multiple RDF serialisation formats (namely, RDF/XML, Turtle, N3, N-Triples, JSON-LD, HTML+RDFa).

The source code of the API is available from the Commission’s Git repository:

<https://webgate.ec.europa.eu/CITnet/stash/projects/ODCKAN/repos/iso-19139-to-dcat-ap/browse/api>

Motivation and use cases
========================

The basic use case that GeoDCAT-AP intends to enable is a cross-domain data portal search for datasets, as documented in the DCAT-AP specification \[DCAT-AP\]. GeoDCAT-AP will make it easier to share descriptions of spatial datasets between spatial data portals and general data portals, and thus help increase public and cross-sector access to such high value datasets. The datasets could include:

-   **Datasets on the INSPIRE Geoportal**. The INSPIRE Geoportal aggregates metadata for over 100k datasets across Europe. It provides the means to search for spatial data sets and spatial data services, and subject to access restrictions, to view spatial data sets from the EU Member States within the framework of the INSPIRE Directive. The metadata stored on this portal is structured according to the INSPIRE Metadata Technical Guidelines \[INSPIRE-MD-TG\]. In order to maximise visibility and re-use, spatial datasets could also be listed on general-purpose Open Data Portals, such as the European Union Open Data Portal (EU ODP)[5] and the European Data Portal (EDP)[6].

<!-- -->

-   **Datasets on national SDIs**. GeoDCAT-AP would facilitate the integration of SDIs operated by EU Member States with any data catalogue able to consume DCAT-AP-compliant metadata.

-   **General geospatial datasets**. The geospatial community shares a common background and makes consistent use of consolidated standards and technologies. In particular, as far as metadata are concerned, it is widespread to use standards like ISO 19115 / 19139, for the representation and encoding of metadata, and OGC’s CSW (Catalog Service for the Web) for accessing and querying metadata records. These standards are also those currently recommended in INSPIRE.

An additional RDF syntax for INSPIRE and ISO 19115 metadata elements is beneficial, especially when other data portals support the DCAT-AP metadata elements only.

Conversion rules to RDF syntax would allow Member States to maintain their collections of INSPIRE-relevant datasets following the INSPIRE Metadata Technical Guidelines based on ISO 19115 and ISO 19119, while at the same time publishing these collections on DCAT-AP-conformant data portals. A conversion to RDF syntax – using for example the GeoDCAT-AP XSLT script \[GEODCAT-XSLT\] - allows additional metadata elements to be displayed on general-purposed data portals, provided that such data portals are capable of displaying of additional metadata elements. Furthermore, data portals frequently are complemented by a triple store, making that the full set of GeoDCAT-AP metadata can be queried through a SPARQL endpoint.

<span id="_Ref430697162" class="anchor"><span id="_Toc447881030" class="anchor"></span></span>Methodology and summary of results
================================================================================================================================

Methodologically, the development of GeoDCAT-AP implied three main interrelated tasks:

1.  Definition of alignment criteria and requirements.

2.  Identification of the metadata elements to be covered by GeoDCAT-AP.

3.  Definition of alignments for the metadata elements to be covered by GeoDCAT-AP.

These tasks and their results are described in the following sections.

Alignment criteria and requirements
-----------------------------------

The objective of the GeoDCAT-AP is twofold:

1.  Provide a DCAT-AP-conformant representation of geospatial metadata.

2.  Provide an as much as possible comprehensive RDF-based representation of geospatial metadata, based on widely used vocabularies (as DCAT-AP), trying, at the same time, to avoid semantic loss and to promote cross-domain re-use.

These two goals, having a different scope and applying to different use cases (see Section 3), are reflected in the two profiles of GeoDCAT-AP, core and extended, described in Section 5.

Note that point (1) implies that:

-   GeoDCAT-AP must include, at least, all the mandatory DCAT-AP elements.

-   Vocabularies different from DCAT-AP can be used only for those geospatial metadata elements not supported in DCAT-AP.

Another key criterion was to base as much as possible the defined alignments on existing practices, in particular those contributed by the GeoDCAT-AP WG. The objective was to build upon experiences having already addressed issues in scope of GeoDCAT-AP, and to avoid a negative impact on existing implementations.

Finally, as already mentioned in Section 1.1, whenever no suitable candidates were available in existing vocabularies to represent geospatial metadata elements, the possibility of defining new terms was not excluded. However, this option needed to be carefully assessed, and discarded whenever it might have led to a specification that was conflicting with standards under preparation. For example, this was the case of the work carried out by the W3C Data on the Web Best Practices Working Group and the joint W3C/OG Spatial Data on the Web Working Group.

As it will be explained in Section 4.3, no new terms have been defined in the current version of GeoDCAT-AP.

<span id="_Ref422247357" class="anchor"><span id="_Toc447881032" class="anchor"></span></span>Metadata elements to be covered by GeoDCAT-AP
-------------------------------------------------------------------------------------------------------------------------------------------

The general criterion used for this task was that GeoDCAT-AP would ideally cover *all* the metadata elements of the core profile of ISO 19115 and those defined in INSPIRE, with the requirement that only *optional* elements *might* be excluded.

Based on this, the current version of GeoDCAT-AP covers the following set of metadata elements:

-   All the metadata elements in the core profile of ISO 19115.

-   All the metadata elements defined in INSPIRE, with the exclusion of those not common to all the INSPIRE spatial data themes.

More precisely, the supported INSPIRE metadata elements include:

-   The set of metadata elements defined in the INSPIRE Metadata Regulation \[INSPIRE-MD-REG\].

-   The set of metadata elements defined in the INSPIRE Data and Services Regulation (Article 13: “Metadata required for Interoperability”) \[INSPIRE-D&S-REG\]. These elements are also listed in Appendix B.1 to the INSPIRE Metadata Technical Guidelines (version 1.3) \[INSPIRE-MD-TG\].

-   The set of metadata elements recommended as common to all the INSPIRE spatial data themes in the INSPIRE Data Specifications Technical Guidelines, and listed in the first table included in Appendix B.2 to version 1.3 of the INSPIRE Metadata Technical Guidelines (version 1.3) \[INSPIRE-MD-TG\]. These elements are the following ones:

    -   Conceptual and domain consistency (Data quality – Logical consistency).

    -   Maintenance information.

The full list of metadata elements covered by the current version of GeoDCAT-AP is available in Annex I to this document.

The metadata elements not supported in the current version of GeoDCAT-AP are those recommended only for *specific* INSPIRE spatial data themes in the INSPIRE Data Specifications Technical Guidelines, and listed in the second, third and fourth table included in Appendix B.2 to the INSPIRE Metadata Technical Guidelines (version 1.3) \[INSPIRE-MD-TG\].

These elements have been excluded in the current version of GeoDCAT-AP for the following reasons:

-   The priority was to support all those elements relevant to any dataset.

-   These elements are all optional.

Support to these metadata elements might be provided in future versions of GeoDCAT-AP.

<span id="_Ref422244630" class="anchor"><span id="_Toc447881033" class="anchor"></span></span>Alignments defined in GeoDCAT-AP
------------------------------------------------------------------------------------------------------------------------------

The alignments defined in the current version of GeoDCAT-AP are the result of an iterative revision process, following the criteria illustrated in the previous sections and the review of the GeoDCAT-AP WG.

The work started with the review of the suite of specifications concerning the INSPIRE profile of DCAT-AP (INSPIRE+DCAT-AP) \[INSPIRE-DCAT\], and of the preliminary proposals concerning the metadata elements not covered by INSPIRE+DCAT-AP.

In two specific cases, feedback has been asked to relevant standardisation bodies, in order to validate the proposal made in GeoDCAT-AP. In particular, this concerned feedback provided by the W3C Provenance Working Group on the use of the W3C PROV ontology to model responsible party roles and conformance results (data quality).

Finally, the GeoDCAT-AP WG has worked in close coordination with the DCAT-AP WG, in order to ensure mutual compliance of the proposed solutions.

The results of this work, reflected in the current version of GeoDCAT-AP, can be summarised as follows:

-   Compliance with DCAT-AP is ensured: The geospatial metadata elements covered by GeoDCAT-AP include all those that in DCAT-AP are mandatory, plus a subset of those that are recommended and optional.

-   GeoDCAT-AP offers alignments for all the metadata elements illustrated in Section 4.2, by using existing vocabularies, and without defining new terms.

The majority of the alignments defined in GeoDCAT-AP provide a complete representation of the corresponding geospatial metadata elements, but some metadata elements have open issues:

-   Partial mappings: For some metadata elements, only a partial mapping is available. This concerns data quality and maintenance information, for which only the mandatory components have been mapped (for more details, see Annex II, Sections II.14 and II.27, respectively). This decision was taken because existing vocabularies did not offer the ability to represent all the components of these metadata elements.

-   Provisional mappings: For some metadata elements, no suitable candidate has been found to model them also partially. This concerns the following elements:

    -   spatial resolution (see Annex II, Section II.13);

    -   data quality and conformity (Annex II, Section II.14);

    -   (coordinate and temporal) reference systems (Annex II, Section II.23).

        The alignments for these elements defined in the current version of GeoDCAT-AP must then be considered as unstable, and are meant to be replaced by appropriate terms defined in standard vocabularies (whether and when available). Notably, both the W3C Data on the Web Best Practices WG and the joint W3C/OGC Spatial Data on the Web Working Group planned to standardise the representation of data granularity (which includes spatial resolution), data quality and conformity, and reference systems.

The details of the alignments defined in GeoDCAT-AP are illustrated in the following section.

<span id="_Ref412533934" class="anchor"><span id="_Toc414637478" class="anchor"><span id="_Ref422243831" class="anchor"><span id="_Ref424139129" class="anchor"><span id="_Toc447881034" class="anchor"></span></span></span></span></span>RDF syntax bindings for INSPIRE and ISO 19115 metadata elements 
===========================================================================================================================================================================================================================================================================================================

The following sections provide the list of the bindings defined in GeoDCAT-AP for the RDF representation of INSPIRE metadata and the core profile of ISO 19115:2003.

For detailed usage notes and examples of each of the metadata elements covered by GeoDCAT-AP, we refer the reader to Annex II (the relevant section is specified in the “comments” column of the mapping table).

<span id="_Toc414637479" class="anchor"><span id="_Toc447881035" class="anchor"></span></span>Used namespaces
-------------------------------------------------------------------------------------------------------------

Table 1 gives an overview of the namespaces (and prefixes) used in the remainder of this document.

<span id="_Ref412474209" class="anchor"><span id="_Toc447881075" class="anchor"></span></span>Table : Namespace prefixes

| Prefix | Namespace                                    | RDF Vocabulary                                                     |
|--------|----------------------------------------------|--------------------------------------------------------------------|
| adms   | http://www.w3.org/ns/adms\#                  | Asset Description Metadata Schema                                  |
| cnt    | http://www.w3.org/2011/content\#             | Representing Content in RDF 1.0                                    |
| dc     | http://purl.org/dc/elements/1.1/             | Dublin Core Metadata Element Set, Version 1.1                      |
| dcat   | http://www.w3.org/ns/dcat\#                  | Data Catalog Vocabulary                                            |
| dct    | http://purl.org/dc/terms/                    | DCMI Metadata Terms                                                |
| dctype | http://purl.org/dc/dcmitype/                 | DCMI Type Vocabulary                                               |
| foaf   | http://xmlns.com/foaf/0.1/                   | FOAF Vocabulary                                                    |
| gsp    | http://www.opengis.net/ont/geosparql\#       | OGC GeoSPARQL                                                      |
| locn   | http://www.w3.org/ns/locn\#                  | ISA Programme Core Location Vocabulary                             |
| owl    | http://www.w3.org/2002/07/owl\#              | OWL Web Ontology Language                                          |
| prov   | http://www.w3.org/ns/prov\#                  | PROV-O: The PROV Ontology                                          |
| rdf    | http://www.w3.org/1999/02/22-rdf-syntax-ns\# | Resource Description Framework (RDF): Concepts and Abstract Syntax |
| rdfs   | http://www.w3.org/2000/01/rdf-schema\#       | RDF Vocabulary Description Language 1.0: RDF Schema                |
| schema | http://schema.org/                           | schema.org                                                         |
| skos   | http://www.w3.org/2004/02/skos/core\#        | SKOS Simple Knowledge Organization System - Reference              |
| vcard  | http://www.w3.org/2006/vcard/ns\#            | vCard Ontology                                                     |
| xsd    | http://www.w3.org/2001/XMLSchema\#           | XML Schema Part 2: Datatypes Second Edition                        |

<span id="_Ref416690026" class="anchor"><span id="_Toc414637480" class="anchor"></span></span>

Overview of bindings for GeoDCAT-AP Core
----------------------------------------

Table 2 provides an overview of **GeoDCAT-AP Core**. This includes bindings for metadata elements of the INSPIRE metadata and metadata elements in the core profile of ISO 19115:2003 core *for which DCAT-AP provides an RDF syntax binding*. Those metadata elements for which DCAT-AP does not provide a binding are part of the GeoDCAT-AP Extended profile described in Section 5.3.

GeoDCAT-AP Core is meant to enable the harvesting and re-use of spatial metadata records through DCAT-AP-conformant applications and services, including data portals and APIs. The alignments for INSPIRE and ISO 19115:2003 metadata elements that are not included in GeoDCAT-AP Core are defined in GeoDCAT-AP Extended, see Section 5.3.

In addition to this, GeoDCAT-AP Core does not provide alignments from metadata records concerning services, with the only exception of catalogue or discovery services, which are the only one supported in DCAT-AP.

In Table 2 the starred elements (\*) are used to indicate the corresponding metadata element in the core profile of ISO 19115:2003. For each element, it is indicated whether the element is mandatory (M), optional (O), conditional (C), or recommended (R) in either specification.

<span id="_Ref416693018" class="anchor"><span id="_Toc447881076" class="anchor"></span></span>Table : Element bindings for GeoDCAT-AP Core

<table>
<thead>
<tr class="header">
<th align="left"><p>INSPIRE metadata</p>
<p>*ISO19115:2003 Core Profile</p></th>
<th align="left">DCAT-AP Property</th>
<th align="left">Domain</th>
<th align="left">Range</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Resource title (M)</p>
<p>*Dataset title (M)</p></td>
<td align="left">dct:title (M)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">rdf:PlainLiteral</td>
<td align="left">See Annex II, Section II.1</td>
</tr>
<tr class="even">
<td align="left"><p>Resource abstract (M)</p>
<p>*Abstract describing the dataset (M)</p></td>
<td align="left">dct:description (M)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">rdf:PlainLiteral</td>
<td align="left">See Annex II, Section II.2</td>
</tr>
<tr class="odd">
<td align="left"><p>Resource type (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left"><p>rdf:type (M)</p>
<p>(see also binding for GeoDCAT-AP Extended)</p></td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left"><p>rdfs:Class (values dcat:Dataset</p>
<p>dcat:Catalog)</p></td>
<td align="left">See Annex II, Section II.3. DCAT-AP does not distinguish between datasets and dataset series. dcat:Catalog can be used for catalogue / discovery services.</td>
</tr>
<tr class="even">
<td align="left"><p>Resource locator (C)</p>
<p>*On-line resource (O)</p></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left">See Annex II, Section II.4. The proposed encoding depends whether the resource is a service or a dataset or data series. Also, the value of the function code (CI_OnlineFunctionCode) must be taken into account.</td>
</tr>
<tr class="odd">
<td align="left"><blockquote>
<p>For services</p>
</blockquote></td>
<td align="left">foaf:homepage</td>
<td align="left"><p>-</p>
<p>(dcat:Catalog (M))</p></td>
<td align="left">foaf:Document</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="even">
<td align="left"><blockquote>
<p>For dataset and data series (function code not provided)</p>
</blockquote></td>
<td align="left">dcat:landingPage (O)</td>
<td align="left">dcat:Dataset (M)</td>
<td align="left">foaf:Document</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="odd">
<td align="left"><blockquote>
<p>For dataset and data series (‘download’ function code)</p>
</blockquote></td>
<td align="left">dcat:accessURL (M)</td>
<td align="left">dcat:Distribution (R)</td>
<td align="left">rdfs:Resource</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="even">
<td align="left"><blockquote>
<p>For dataset and data series (‘information’ function code)</p>
</blockquote></td>
<td align="left">foaf:page (not in DCAT-AP!)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M))</p></td>
<td align="left">foaf:Document</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="odd">
<td align="left"><blockquote>
<p>For dataset and data series (‘offlineAccess’ function code)</p>
</blockquote></td>
<td align="left">dcat:accessURL (M)</td>
<td align="left">dcat:Distribution (R)</td>
<td align="left">rdfs:Resource</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="even">
<td align="left"><blockquote>
<p>For dataset and data series (‘order’ function code)</p>
</blockquote></td>
<td align="left">dcat:accessURL (M)</td>
<td align="left">dcat:Distribution (R)</td>
<td align="left">rdfs:Resource</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="odd">
<td align="left"><blockquote>
<p>For dataset and data series (‘search’ function code)</p>
</blockquote></td>
<td align="left">foaf:page</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset)</p></td>
<td align="left">foaf:Document</td>
<td align="left">See Annex II, Section II.4.</td>
</tr>
<tr class="even">
<td align="left"><p>Unique resource identifier (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left">dct:identifier (O)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M))</p></td>
<td align="left">rdfs:Literal</td>
<td align="left">See Annex II, Section II.5. In RDF, this could also be represented as the URI of the dataset.</td>
</tr>
<tr class="odd">
<td align="left"><p>Resource language (C)</p>
<p>*Dataset language (M)</p></td>
<td align="left">dct:language (O for dcat:Dataset and R for dcat:Catalog)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">dct:LinguisticSystem</td>
<td align="left">See Annex II, Section II.7.</td>
</tr>
<tr class="even">
<td align="left"><p>Spatial data service type (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left">rdf:type</td>
<td align="left">-</td>
<td align="left"><p>rdfs:Class (values</p>
<p>dcat:Catalog)</p></td>
<td align="left">See Annex II, Section II.3. DCAT-AP foresees only one type of services - i.e., data catalogues.</td>
</tr>
<tr class="odd">
<td align="left"><p>Keyword value (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left"><p>dcat:keyword (R)</p>
<p>dcat:theme (R)</p>
<p>(see also binding for GeoDCAT-AP Extended)</p></td>
<td align="left">dcat:Dataset (M)</td>
<td align="left">rdfs:Literal</td>
<td align="left"><p>See Annex II, Section II.8. For datasets and data series, dcat:keyword is used for free keywords; dcat:theme for controlled vocabularies.</p>
<p>Keywords whose controlled vocabulary is the one of the INSPIRE spatial data themes are mapped to dcat:theme, and expressed by the corresponding URI in the INSPIRE Registry. See controlled vocabulary for theme in Section 6.</p>
<p>For services a syntax binding is provided in GeoDCAT-AP Extended only.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Geographic bounding box (M)</p>
<p>*Geographic location of the dataset (by four coordinates or by geographic identifier) (C)</p></td>
<td align="left">dct:spatial (O)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">dct:Location</td>
<td align="left">See Annex II, Section II.10 on the preferred format to be used in RDF for the representation of geometries.</td>
</tr>
<tr class="odd">
<td align="left"><p>Temporal extent (C)</p>
<p>*Additional extent information for the dataset (vertical and temporal) (O)</p></td>
<td align="left">dct:temporal (O)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset</p>
<p>(M))</p></td>
<td align="left">dct:PeriodOfTime</td>
<td align="left">See Annex II, Section II.11.</td>
</tr>
<tr class="even">
<td align="left"><p>Date of publication (C)</p>
<p>*Dataset reference date (M) – publication</p></td>
<td align="left">dct:issued (R for dcat:Catalog and O for dcat:Dataset)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">xsd:date</td>
<td align="left">See Annex II, Section II.11.</td>
</tr>
<tr class="odd">
<td align="left"><p>Date of last revision (C)</p>
<p>*Dataset reference date (M) – revision</p></td>
<td align="left">dct:modified (R for dcat:Catalog and O for dcat:Dataset)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">xsd:date</td>
<td align="left">See Annex II, Section II.11.</td>
</tr>
<tr class="even">
<td align="left"><p>Lineage (M)</p>
<p>*Lineage (O)</p></td>
<td align="left">dct:provenance</td>
<td align="left"><p>-</p>
<p>-</p>
<p>(dcat:Dataset (M),</p>
<p>dcat:Catalog (M))</p></td>
<td align="left">dct:ProvenanceStatement</td>
<td align="left">See Annex II, Section II.12.</td>
</tr>
<tr class="odd">
<td align="left"><p>Conformity (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left"><p>dct:conformsTo (O)</p>
<p>(see also binding for GeoDCAT-AP Extended)</p></td>
<td align="left"><p>-</p>
<p>(dcat:Dataset</p>
<p>(M))</p></td>
<td align="left">dct:Standard</td>
<td align="left">See Annex II, Section II.14. dct:conformsTo can model only one of the cases foreseen in INSPIRE. i.e., when the degree of conformity is “conformant”.</td>
</tr>
<tr class="even">
<td align="left"><p>Conformity Specification (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left"><p>dct:title</p>
<p>dct:issued, dct:modified, dct:created</p>
<p>(see also binding for GeoDCAT-AP Extended)</p></td>
<td align="left">rdfs:Resource</td>
<td align="left"><p>rdf:PlainLiteral</p>
<p>xsd:date</p></td>
<td align="left">See Annex II, Section II.14.</td>
</tr>
<tr class="odd">
<td align="left"><p>Conditions for access and use (M)</p>
<p>*not in ISO19115 core</p></td>
<td align="left">dct:license (O)</td>
<td align="left"><p>-</p>
<p>(dcat:Distribution (R))</p></td>
<td align="left">dct:LicenseDocument</td>
<td align="left">See Annex II, Section II.15.</td>
</tr>
<tr class="even">
<td align="left"><p>Limitations on public access (C)</p>
<p>*not in ISO19115 core</p></td>
<td align="left">dct:accessRights (O)</td>
<td align="left"><p>-</p>
<p>(dcat:Distribution (R))</p></td>
<td align="left">dct:RightsStatement</td>
<td align="left">See Annex II, Section II.15.</td>
</tr>
<tr class="odd">
<td align="left"><p>Responsible party (M)</p>
<p>*Dataset responsible party (O)</p></td>
<td align="left">dct:publisher (R), dcat:contactPoint (R)</td>
<td align="left"><p>-</p>
<p>(dcat:Dataset (M))</p></td>
<td align="left"><p>dct:Agent</p>
<p>vcard:Kind</p></td>
<td align="left">See Annex II, Section II.16. DCAT-AP foresees only 2 of the 11 responsible party roles supported in INSPIRE. GeoDCAT-AP Extended suggests the use of the W3C PROV ontology to model information concerning provenance not covered in DCAT-AP.</td>
</tr>
<tr class="even">
<td align="left"><p>Encoding (M)</p>
<p>*Distribution format (O)</p></td>
<td align="left">dct:format (R), dcat:mediaType (O)</td>
<td align="left">dcat:Distribution (R)</td>
<td align="left">dc:MediaTypeOrExtent</td>
<td align="left">See Annex II, Section II.25. See controlled vocabularies for encoding in Section 6.</td>
</tr>
<tr class="odd">
<td align="left"><p>Maintenance information (R)</p>
<p>*not in ISO19115 core</p></td>
<td align="left">dct:accrualPeriodicity (O)</td>
<td align="left"><p>dctype:Collection</p>
<p>(dcat:Dataset) (M)</p></td>
<td align="left">dct:Frequency</td>
<td align="left">See Annex II, Section II.27.</td>
</tr>
<tr class="even">
<td align="left"><em>-Metadata standard</em></td>
<td align="left">dct:conformsTo (R)</td>
<td align="left"><p>-</p>
<p>(dcat:CatalogRecord (O))</p></td>
<td align="left">dct:Standard</td>
<td align="left">See Annex II, Section II.18. This element, not existing in ISO 19115, is just meant to provide the context for the specification of the metadata standard name and version.</td>
</tr>
<tr class="odd">
<td align="left">*Metadata standard name (O)</td>
<td align="left">dct:title</td>
<td align="left"><p>-</p>
<p>(dct:Standard (O))</p></td>
<td align="left">rdf:PlainLiteral</td>
<td align="left">See Annex II, Section II.18.</td>
</tr>
<tr class="even">
<td align="left">*Metadata standard version (O)</td>
<td align="left">owl:versionInfo</td>
<td align="left"><p>-</p>
<p>(dct:Standard (O))</p></td>
<td align="left">rdfs:Literal</td>
<td align="left">See Annex II, Section II.18. This can be part of the information specified for metadata standard name.</td>
</tr>
<tr class="odd">
<td align="left"><p>Metadata date (M)</p>
<p>*Metadata date stamp (M)</p></td>
<td align="left">dct:modified (M)</td>
<td align="left"><p>-</p>
<p>(dcat:CatalogRecord (O))</p></td>
<td align="left">xsd:date</td>
<td align="left">See Annex II, Section II.11.</td>
</tr>
<tr class="even">
<td align="left"><p>Metadata language (M)</p>
<p>*Metadata language (C)</p></td>
<td align="left">dct:language (O)</td>
<td align="left"><p>-</p>
<p>(dcat:CatalogRecord (O))</p></td>
<td align="left">dct:LinguisticSystem</td>
<td align="left">See Annex II, Section II.7.</td>
</tr>
</tbody>
</table>

<span id="_Ref422129177" class="anchor"><span id="_Ref422159008" class="anchor"></span></span>

Overview of bindings for GeoDCAT-AP Extended
--------------------------------------------

This section provides an overview of the RDF syntax bindings in GeoDCAT-AP Extended. This GeoDCAT-AP profile covers elements defined in INSPIRE and the core profile of ISO 19115:2003, for which DCAT-AP does not provide a syntax binding. GeoDCAT-AP Extended is a *superset* of GeoDCAT-AP Core.

Table 3 contains the suggested RDF syntax binding for INSPIRE metadata. In the table below, the starred elements (\*) are used to indicate the corresponding metadata element in the core profile of ISO 19115:2003. For each metadata element, it is indicated whether the element is mandatory (M), optional (O), conditional (C), or recommended (R) in either specification.

Please note that some metadata elements have an RDF syntax binding in both the GeoDCAT-AP Core and Extended profile. These elements fall in one of these categories:

1.  **Partial coverage by a DCAT-AP binding**: This concerns conformity (only degree of conformity conformant is supported) and responsible organisation (only responsible party roles publisher and point of contact are supported).

2.  **Subsumption by a GeoDCAT-AP RDF binding**: ISO metadata elements available in GeoDCAT-AP Core, but for which only a many-to-one mapping is supported in DCAT-AP. This concerns resource types, since the DCAT notion of dataset models both the ISO/INSPIRE notions of data set and data series; the DCAT notion of data catalogue models only one of the types of spatial data services.

In order to preserve the original semantics, the extended profile of GeoDCAT-AP defines additional mappings to those included in GeoDCAT-AP Core. The two sets of alignments are not mutually exclusive, and can coexist without creating conflicts.

<span id="_Ref412464289" class="anchor"><span id="_Toc447881077" class="anchor"></span></span>Table : Element bindings for GeoDCAT-AP Extended

| INSPIRE metadata                                                               
                                                                                 
 \*ISO19115:2003 Core Profile                                                    | Property                     | Domain                   | Range                     | Comments                                                                                                                                           |
|--------------------------------------------------------------------------------|------------------------------|--------------------------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Resource type (M)                                                              
                                                                                 
 \*not in ISO19115                                                               | dct:type                     | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M),        
                                                                                                                                           
                                                                                                                 dcat:Catalog (M))         | rdfs:Class                
                                                                                                                                                                       
                                                                                                                                            (skos:Concept)             | See Annex II, Section II.3 and the controlled vocabulary for resource type in Section 6. DCAT-AP foresees the use of dct:type on dct:Dataset only. |
| Topic category (M)                                                             
                                                                                 
 \*Dataset topic category (M)                                                    | dct:subject                  | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M))        | -                         
                                                                                                                                                                       
                                                                                                                                            (skos:Concept)             | See Annex II, Section II.8 and the controlled vocabulary for topic category in Section 6.                                                          |
| Spatial data service type (M)                                                  
                                                                                 
 \*not in ISO19115                                                               | dct:type                     | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M),        
                                                                                                                                           
                                                                                                                 dcat:Catalog (M),         
                                                                                                                                           
                                                                                                                 dctype:Service)           | rdfs:Class                
                                                                                                                                                                       
                                                                                                                                            (skos:Concept)             | See Annex II, Section II.3. See controlled vocabulary for spatial data service type in Section 6.                                                  |
| Keyword value (M)                                                              
                                                                                 
 \*not in ISO19115 core                                                          | dc:subject                   
                                                                                                                
                                                                                  dct:subject                   
                                                                                                                
                                                                                  dct:type                      | - (dcat:Catalog (M))     | - (rdfs:Literal)          
                                                                                                                                                                       
                                                                                                                                            - (rdfs:Resource)          
                                                                                                                                                                       
                                                                                                                                            rdfs:Class (skos:Concept)  | See Annex II, Section II.8.2.                                                                                                                      |
| Originating controlled vocabulary (C)                                          
                                                                                 
 \*not in ISO19115 core                                                          | skos:inScheme                | skos:Concept             | skos:ConceptScheme        | See Annex II, Section II.8.                                                                                                                        |
| Date of creation (C)                                                           
                                                                                 
 \*Dataset reference date (M) - creation                                         | dct:created                  | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M),        
                                                                                                                                           
                                                                                                                 dcat:Catalog (M))         | xsd:date                  | See Annex II, Section II.11.                                                                                                                       |
| Spatial resolution (C)                                                         
                                                                                 
 \*Spatial resolution of the dataset (O)                                         | rdfs:comment                 | -                        | rdfs:Literal              | See Annex II, Section II.13. Spatial resolution is encoded in a human-readable form only.                                                          |
| Conformity (M)                                                                 
                                                                                 
 \*not in ISO19115 core                                                          | prov:wasUsedBy               | prov:Entity              
                                                                                                                                           
                                                                                                                 (dcat:DataSet (M))        | prov:Activity             | See Annex II, Section II.14.                                                                                                                       |
| Conformity Specification (M)                                                   
                                                                                 
 \*not in ISO19115 core                                                          | prov:wasDerivedFrom          | prov:Entity              | prov:Entity               | See Annex II, Section II.14.                                                                                                                       |
| Conformity degree (M)                                                          
                                                                                 
 \*not in ISO19115 core                                                          | prov:generated               | prov:Activity            | prov:Entity               | See Annex II, Section II.14 and the controlled vocabulary for conformity degree in Section 6.                                                      |
| Topological Consistency (C)                                                    
                                                                                 
 \*not in ISO19115 core                                                          | -                            | -                        | -                         | See Annex II, Section II.14. No syntax binding is provided for data quality, other than data conformity.                                           |
| Data Quality – Logical Consistency –                                           
                                                                                 
 Conceptual Consistency, Domain Consistency – (R)                                
                                                                                 
 \*not in ISO19115 core                                                          | -                            | -                        | -                         | See Annex II, Section II.14. No syntax binding is provided for data quality, other than conformity.                                                |
| Responsible party (M)                                                          
                                                                                 
 \*Dataset responsible party (O)                                                 | dct:creator                  | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M))        | dct:Agent                 | See Annex II, Section II.16.                                                                                                                       |
|                                                                                | prov:qualifiedAttribution    | prov:Entity              
                                                                                                                                           
                                                                                                                 (dcat:Dataset (M))        | prov:Attribution          |                                                                                                                                                    |
| Responsible party role (M)                                                     | dct:type                     | -                        
                                                                                                                                           
                                                                                                                 (prov:Attribution)        | rdfs:Class                | See Annex II, Section II.16 and controlled vocabulary for responsible party role in Section 6.                                                     |
| \*Metadata file identifier (O)                                                 | dct:identifier               | -                        
                                                                                                                                           
                                                                                                                 (dcat:CatalogRecord (O))  | rdfs:Literal              | See Annex II, Section II.17. In RDF, this could also be represented as the URI of the metadata / catalogue record.                                 |
| Metadata point of contact (M)                                                  
                                                                                 
 \*Metadata point of contact (M)                                                 | prov:qualifiedAttribution    | -                        
                                                                                                                                           
                                                                                                                 (dcat:CatalogRecord (O))  | prov:Attribution          | See Annex II, Section II.16.                                                                                                                       |
|                                                                                | dcat:contactPoint            | -                        
                                                                                                                                           
                                                                                                                 (dcat:CatalogRecord (O))  | vcard:Kind                | See Annex II, Section II.16.                                                                                                                       |
| \*Metadata character set (C)                                                   | cnt:characterEncoding        | cnt:Content              
                                                                                                                                           
                                                                                                                 (dcat:CatalogRecord (O))  | rdfs:Literal              | See Annex II, Section II.24.                                                                                                                       |
| <span id="_Ref412464480" class="anchor"></span>Coordinate Reference System (M) 
                                                                                 
 \*Reference System (0)                                                          | dct:conformsTo               | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset             
                                                                                                                                           
                                                                                                                 (M))                      | dct:Standard              | See Annex II, Section II.23.                                                                                                                       |
| Temporal Reference System (C)                                                  
                                                                                 
 \*Reference System (0)                                                          | dct:conformsTo               | -                        
                                                                                                                                           
                                                                                                                 (dcat:Dataset             
                                                                                                                                           
                                                                                                                 (M))                      | dct:Standard              | See Annex II, Section II.23.                                                                                                                       |
| Character Encoding (C)                                                         
                                                                                 
 \*Dataset character set (C)                                                     | cnt:characterEncoding        | cnt:Content              
                                                                                                                                           
                                                                                                                 (dcat:Distribution (R))   | rdfs:Literal              | See Annex II, Section II.24.                                                                                                                       |
| Spatial representation type – (M)                                              
                                                                                 
 \*Spatial representation type (O)                                               | adms:representationTechnique | dcat:Distribution (R)    | skos:Concept              | See Annex II, Section II.26.                                                                                                                       |

<span id="_Toc414637481" class="anchor"></span>

<span id="_Ref412408166" class="anchor"><span id="_Toc414637503" class="anchor"><span id="_Toc447881038" class="anchor"></span></span></span>Controlled vocabularies
====================================================================================================================================================================

This section lists the controlled vocabularies that must be used according to the GeoDCAT-AP Core Profile and the GeoDCAT-AP Extended Profile.

<span id="_Toc447881078" class="anchor"></span>Table : Controlled vocabularies to be used

| Element(s) in INSPIRE Metadata Regulation                   
                                                              
 \*ISO19115:2003 Core Profile                                 | Property                     | Controlled Vocabulary                                                                                                                                                      | Comment                                                                                                                                                                                                            |
|-------------------------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Resource language                                           
                                                              
 Metadata language                                            
                                                              
 (ISO 639-2)                                                  | dct:language                 | Language Named Authority List \[MDR-LANG\] operated by the Metadata Registry of the Publications Office of the EU                                                          
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/resource/authority/language>                                                                                                                 |                                                                                                                                                                                                                    |
| Resource type                                               | dct:type                     | Register operated by the INSPIRE Registry for resource types defined in ISO 19115                                                                                          
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/ResourceType>                                                                                                                | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Spatial data service type                                   | dct:type                     | Register operated by the INSPIRE Registry for service types                                                                                                                
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType>                                                                                                      | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Topic category                                              | dct:subject                  | Register operated by the INSPIRE Registry for topic categories defined in ISO 19115                                                                                        
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/TopicCategory>                                                                                                               | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Keyword denoting one of the INSPIRE spatial data themes     | dcat:theme                   | INSPIRE spatial data theme register operated by the INSPIRE Registry                                                                                                       
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/theme>                                                                                                                                         |                                                                                                                                                                                                                    |
| MDR Data Themes                                             | dcat:theme                   | Data Theme Named Authority List \[MDR-THEMES\] operated by the Metadata Registry of the Publications Office of the EU                                                      
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/resource/authority/data-theme>                                                                                                               | Required for compliance with DCAT-AP. See Annex II, Section II.8 for more details.                                                                                                                                 |
| Keyword denoting one of the spatial data service categories | dct:type                     | Register operated by the INSPIRE Registry for spatial data service categories defined in ISO 19119                                                                         
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory>                                                                                                  | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Conformity degree                                           | dct:type                     | Register operated by the INSPIRE Registry for degrees of conformity                                                                                                        
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity>                                                                                                          | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Responsible party role                                      | dct:type                     | Register operated by the INSPIRE Registry for responsible party roles                                                                                                      
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole>                                                                                                        | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Encoding                                                    | dct:format                   | File type Named Authority List \[MDR-FT\] operated by the Metadata Registry of the Publications Office of the EU                                                           
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/resource/authority/file-type>                                                                                                                |                                                                                                                                                                                                                    |
|                                                             |                              | For formats not (yet) included into \[MDR-FT\], the media type register for datasets in INSPIRE download services is to be used \[INSPIRE-MT\].                            
                                                                                                                                                                                                                                                                          
                                                                                              <http://inspire.ec.europa.eu/media-types>                                                                                                                                   | GeoDCAT-AP Extended profile only                                                                                                                                                                                   |
| Character encoding - \*Character sets                       | cnt:characterEncoding        | Register of Character Sets operated by IANA \[IANA-CS\].                                                                                                                   
                                                                                                                                                                                                                                                                          
                                                                                              <http://www.iana.org/assignments/character-sets/>                                                                                                                           | See mapping table in Annex II, Section II.24.                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                           GeoDCAT-AP Extended profile only.                                                                                                                                                                                   |
| Coordinate reference system                                 | dct:conformsTo               | Register of coordinate reference systems included in the European Petroleum Survey Group (EPSG) Geodetic Parameter Dataset.                                                
                                                                                                                                                                                                                                                                          
                                                                                              <http://www.opengis.net/def/crs/EPSG/>                                                                                                                                      
                                                                                                                                                                                                                                                                          
                                                                                              <http://www.epsg-registry.org/>                                                                                                                                             | GeoDCAT-AP Extended profile only.                                                                                                                                                                                  |
| Spatial representation types                                | adms:representationTechnique | The ISO 19115 code list of spatial representation types might be in the future available as a URI register from the INSPIRE Registry.                                      | See mapping table in Annex II, Section II.26.                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                           GeoDCAT-AP Extended profile only.                                                                                                                                                                                   |
| Maintenance frequency                                       | dct:accrualPeriodicity       | MDR Frequency Named Authority List \[MDR-FREQ\].                                                                                                                           
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/resource/authority/frequency>                                                                                                                | See mapping table in Annex II, Section II.27.                                                                                                                                                                      |
|                                                             |                              | For the frequency codes not covered by the MDR Frequency code list, GeoDCAT-AP will use the code list of ISO maintenance frequency codes operated by the INSPIRE Registry. | GeoDCAT-AP Extended profile only                                                                                                                                                                                   |
| Geographic identifier                                       | dct:spatial                  | The continents, countries and places Named Authority Lists operated by the Metadata Registry of the Publications Office of the EU \[MDR-CONT, MDR-COUNTRIES, MDR-PLACES\]. 
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/mdr/authority/continent/>                                                                                                                    
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/mdr/authority/place/>                                                                                                                        
                                                                                                                                                                                                                                                                          
                                                                                              <http://publications.europa.eu/mdr/authority/country/>                                                                                                                      
                                                                                                                                                                                                                                                                          
                                                                                              The geonames URI sets \[GEONAMES\]. <http://www.geonames.org/>                                                                                                              | The MDR Name Authority Lists must be used for continents, countries and places that are in those lists; if a particular location is not in one of the mentioned Named Authority Lists, Geonames URIs must be used. |

Other controlled vocabularies can be used *in addition* to those mentioned above. For example, the working group has identified the following vocabularies:

-   **Geographic identifiers**:

    -   **For marine regions: **

        -   Marine Regions <http://www.marineregions.org/>

        -   SeaVoX salt and fresh water body gazetteer - <https://www.bodc.ac.uk/data/codes_and_formats/seavox/>

    -   **General:**

        -   DBpedia for Geographic Placenames- <http://dbpedia.org/about>

        -   National gazetteer vocabularies where feasible

        -   SeaVoX salt and fresh water body gazetteer for ‘marine geonames’ - <https://www.bodc.ac.uk/data/codes_and_formats/seavox/>

-   **Keywords (with controlled vocabularies):**

    -   **For discipline**: suggested vocabularies are

        -   GEneral Multilingual Environmental Thesaurus (GEMET) - <https://www.eionet.europa.eu/gemet/>

    -   **General: **

        -   GEOSS Societal Benefit Areas - <https://en.wikipedia.org/wiki/Societal_Benefit_Areas>

        -   GEneral Multilingual Environmental Thesaurus (GEMET)- <https://www.eionet.europa.eu/gemet/>

        -   British Oceanographic Data centre - <http://www.bodc.ac.uk/>

<span id="_Toc414637505" class="anchor"><span id="_Toc447881039" class="anchor"></span></span>Acknowledgements
==============================================================================================================

This work was elaborated by a Working Group under the ISA programme. The Working Group was chaired by **Andrea Perego** from the Joint Research Centre of the European Commission. The ISA Programme of the European Commission was represented by **Vassilios Peristeras** and **Athanasios Karalopoulos**. **Andrea Perego** and **Stijn Goedertier** were the editors of the specification.

A special acknowledgement is due to **Antonio Rotundo**, from Agenzia per l’Italia Digitale, who contributed a study comparing INSPIRE and ISO 19115-1:2014, included in Annex III to this specification.

The following table lists all the people who contributed to the development and revision of this specification, either as members of the GeoDCAT-AP Working Group or as external reviewers.

| Name                       | Organisation                                                           | Data portal / project                                              | Country |
|----------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------|---------|
| Adrià Mercader             | OKFN                                                                   | CKAN                                                               | UK      |
| Aleš Veršič                | Ministry of Public Administration                                      | geoportal.gov.si                                                   | SI      |
| Alessio Dragoni            | SCIAMlab                                                               | dati.minambiente.it                                                | IT      |
| Ana Fernández de Soria     | PwC EU Services                                                        | SEMIC project                                                      | EU      |
| Anastasia Dimou            | iMinds / Ghent University                                              |                                                                    | BE      |
| Anders Friis­-Christensen  | European Commission - Joint Research Centre                            | JRC Data Catalogue                                                 | EU      |
| Andrea Perego              | European Commission - Joint Research Centre                            | JRC Data Catalogue, INSPIRE Geoportal                              | EU      |
| Angelos Tzotsos            | IMIS Athena Research Centre                                            | data.gov.gr and geodata.gov.gr                                     | EL      |
| Anja Loddenkemper          | Landesamt für Geoinformation und Landesvermessung Niedersachsen (LGLN) | Spatial Data Infrastructure Lower Saxony                           | DE      |
| Antoine Isaac              | Vrije Universiteit                                                     | Europeana                                                          | NL      |
| Antonio Rotundo            | Agenzia per l’Italia Digitale                                          | Repertorio Nazionale dei Dati Territoriali (RNDT): www.rndt.gov.it | IT      |
| Armin Retterath            | Zentrale Stelle Geodateninfrastruktur                                  
                                                                                                      
                              Rheinland-Pfalz                                                         | geoportal.rlp.de                                                   | DE      |
| Athanasios Karalopoulos    | European Commission                                                    | ISA Programme                                                      | EU      |
| Bert Van Nuffelen          | Tenforce                                                               | Open Data Support project                                          | EU      |
| Chrysi Tsinaraki           | European Commission - Joint Research Centre                            | JRC Data Catalogue                                                 | EU      |
| David Read                 | Data.gov.uk                                                            | data.gov.uk                                                        | UK      |
| Deirdre Lee                | Derilinx                                                               | data.gov.ie                                                        | IE      |
| Eliane Roos                | Institut géographique national (IGN)                                   | geoportail.gouv.fr                                                 | FR      |
| Franks Knibbe              | Geodan                                                                 |                                                                    | NL      |
| Georges Charlot            | GIS team of Brussels Regional Informatics Centre (BRIC)                |                                                                    | BE      |
| Geraldine Nolf             | AGIV                                                                   | geopunt.be                                                         | BE      |
| Hannes Reuter              | GISCO Team at Eurostat                                                 |                                                                    | EU      |
| Hans Overbeek              | Kennis- en Exploitatiecentrum Officiële Overheidspublicaties (KOOP)    | data.overheid.nl                                                   | NL      |
| Ine de Visser              | Geonovum                                                               | nationaalgeoregister.nl                                            | NL      |
| James Passmore             | British Geological Survey                                              |                                                                    | UK      |
| Jan Hjelmager              | Danish Geodata Agency                                                  |                                                                    | DK      |
| Jon Blower                 | University of Reading                                                  | MELODIES EU project                                                | UK      |
| Jorgen Van den Langenbergh | PwC EU Services                                                        | SEMIC project                                                      | EU      |
| Kostas Patroumpas          | IMIS - Athena Research Center                                          |                                                                    | EL      |
| Lorena Hernandez Quiroz    | European Commission - Joint Research Centre                            | INSPIRE Geoportal                                                  | EU      |
| Lorenzino Vaccari          | European Commission - Joint Research Centre                            | JRC Data Catalogue                                                 | EU      |
| Maik Riechert              | University of Reading                                                  | MELODIES EU project                                                | UK      |
| Makx Dekkers               | AMI Consult                                                            | SEMIC project                                                      | NL      |
| Martin Seiler              | National Spatial Data Infrastructure                                   | [www.geoportal.de](http://www.geoportal.de)                        | DE      |
| Matthias Palmér            | MetaSolutions AB                                                       |                                                                    | SE      |
| Michael Lutz               | European Commission - Joint Research Centre                            | INSPIRE Geoportal                                                  | EU      |
| Michael Östling            | MetaGIS                                                                |                                                                    | SE      |
| Paul Smits                 | European Commission - Joint Research Centre                            | INSPIRE Geoportal                                                  | EU      |
| Paul van Genuchten         | GEOCAT                                                                 | GeoNetwork                                                         | NL      |
| Pedro Gonçalves            | Terradue                                                               |                                                                    | IT      |
| Piergiorgio Cipriano       | Sinergis                                                               |                                                                    | IT      |
| Pierluigi Cara             | Italian Civil Protection – Open data Group                             |                                                                    | IT      |
| Pieter Colpaert            | iMinds / Ghent University / Open Knowledge Belgium                     |                                                                    | BE      |
| Simon Cox                  | CSIRO                                                                  |                                                                    | AU      |
| Simon Dutkowski            | Fraunhofer FOKUS                                                       | [www.govdata.de](http://www.govdata.de), European Data Portal      | DE      |
| Stephan Kafka              | Help Service Remote Sensing, Ltd.                                      | Czech national INSPIRE Geoportal                                   | CZ      |
| Stijn Goedertier           | PwC EU Services                                                        | SEMIC project                                                      | EU      |
| Susanne Wigard             | European Commission                                                    |                                                                    | EU      |
| Trevor Alcorn              | Marine Institute                                                       | [data.marine.ie](http://data.marine.ie/)                           | IE      |
| Udo Einspanier             | Con Terra                                                              | European Data Portal                                               | DE      |
| Willem Van Gemert          | Publications Office of the EU                                          | Metadata Registry                                                  | EU      |
| Wouter Schaubroeck         | Hewlett-Packard                                                        |                                                                    | BE      |

References
==========

| \[BCP47\]           | IETF, “IEFT BCP 47 Tags for Identifying Languages,” 2009. \[Online\]. Available: <http://tools.ietf.org/html/bcp47>                                                                                                                                                                                                       |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \[CLD-FREQ\]        | DCMI, “Dublin Core Collection Description Frequency Vocabulary,” 2007. \[Online\]. Available: <http://dublincore.org/groups/collections/frequency/>                                                                                                                                                                       |
| \[CNT\]             | W3C, “Representing Content in RDF - W3C Content Vocabulary,” \[Online\]. Available: <http://www.w3.org/TR/Content-in-RDF10/>                                                                                                                                                                                              |
| \[CSW\]             | Open Geospatial Consortium, “Catalogue Services Specification 2.0.2, OGC 07-045, ISO Metadata Application Profile for CSW 2.0,” 2007. \[Online\]. Available: <http://www.opengeospatial.org/standards/cat>                                                                                                                |
| \[DCAT\]            | W3C, “Data Catalog Vocabulary (DCAT),” 2014. \[Online\]. Available: <http://www.w3.org/TR/vocab-dcat/>                                                                                                                                                                                                                    |
| \[DCAT-AP\]         | European Commission, ISA Programme, “DCAT Application Profile for data portals in Europe,” 2015. \[Online\]. Available: <https://joinup.ec.europa.eu/node/63567>                                                                                                                                                          |
| \[DCTERMS\]         | DCMI, “DCMI Metadata Terms,” 2012. \[Online\]. Available: <http://dublincore.org/documents/2012/06/14/dcmi-terms/>                                                                                                                                                                                                        |
| \[DCWIKI\]          | DCMI, “User Guide / Publishing Metadata,” \[Online\]. Available: <http://wiki.dublincore.org/index.php/User_Guide/Publishing_Metadata>                                                                                                                                                                                    |
| \[EARL\]            | W3C, “W3C Evaluation and Report Language (EARL),” 2011. \[Online\]. Available: <http://www.w3.org/TR/EARL10-Schema/>                                                                                                                                                                                                      |
| \[GEODCAT-XSLT\]    | A. Perego, “XSLT for converting ISO 19139 metadata into DCAT-AP,” 2015. \[Online\]. Available: <https://webgate.ec.europa.eu/CITnet/stash/projects/ODCKAN/repos/iso-19139-to-dcat-ap/>                                                                                                                                    |
| \[GEOHASH\]         | Wikipedia, “Geohash,” \[Online\]. Available: <http://en.wikipedia.org/wiki/Geohash>                                                                                                                                                                                                                                       |
| \[GEOHASH-36\]      | Wikipedia, “Geohash-36,” \[Online\]. Available: <http://en.wikipedia.org/wiki/Geohash-36>                                                                                                                                                                                                                                 |
| \[GEOJSON\]         | H. Butler, M. Daly, A. Doyle, S. Gillies, T. Schaub and C. Schmidt, “The GeoJSON Format Specification,” 2008. \[Online\]. Available: <http://geojson.org/geojson-spec.html>                                                                                                                                               |
| \[GEONAMES\]        | geonames.org, “Geonames.org,” \[Online\]. Available: <http://www.geonames.org/>                                                                                                                                                                                                                                           |
| \[GEOSPARQL\]       | Open Geospatial Consortium, “GeoSPARQL - A Geographic Query Language for RDF Data,” 2012. \[Online\]. Available: <http://www.opengeospatial.org/standards/geosparql>                                                                                                                                                      |
| \[GML\]             | Open Geospatial Consortium, “Geography Markup Language,” \[Online\]. Available: <http://www.opengeospatial.org/standards/gml>                                                                                                                                                                                             |
| \[IANA-CS\]         | IANA, “Character Sets,” \[Online\]. Available: <http://www.iana.org/assignments/character-sets/character-sets.xhtml>                                                                                                                                                                                                      |
| \[IANA-MT\]         | IANA, “Media Types Register,” \[Online\]. Available: <http://www.iana.org/assignments/media-types/media-types.xhtml>                                                                                                                                                                                                      |
| \[INSPIRE-D&S-REG\] | European Commission, “Commission Regulation (EU) No 1089/2010 of 23 November 2010 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards interoperability of spatial data sets and services,” 2010. \[Online\]. Available: <http://eur-lex.europa.eu/eli/reg/com/2010/1089> .          |
| \[INSPIRE-DC\]      | European Commission, “State of progress in the development of guidelines to express elements of the INSPIRE metadata implementing rules using ISO 15836 (Dublin core),” \[Online\]. Available: <http://inspire.ec.europa.eu/reports/ImplementingRules/metadata/MD_IR_and_DC_state%20of%20progress.pdf>                    |
| \[INSPIRE-DCAT\]    | INSPIRE Maintenance and Implementation Group, “Alignment of INSPIRE metadata with DCAT-AP,” 2014. \[Online\]. Available: <https://ies-svn.jrc.ec.europa.eu/projects/metadata/wiki/Alignment_of_INSPIRE_metadata_with_DCAT-AP>                                                                                             |
| \[INSPIRE-DIR\]     | European Parliament, “DIRECTIVE 2007/2/EC OF THE EUROPEAN PARLIAMENT AND OF THE COUNCIL of 14 March 2007 establishing an Infrastructure for Spatial Information in the European Community (INSPIRE),” 2007. \[Online\]. Available: <http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2007:108:0001:0014:en:PDF> |
| \[INSPIRE-DS-TG\]   | European Commission, “Technical Guidance for the implementation of INSPIRE Discovery Services. Version 3.1,” 2011. \[Online\]. Available: <http://inspire.jrc.ec.europa.eu/documents/Network_Services/TechnicalGuidance_DiscoveryServices_v3.1.pdf>                                                                       |
| \[INSPIRE-MD-REG\]  | European Commission, “Commission Regulation (EC) No 1205/2008 of 3 December 2008 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards metadata,” 2008. \[Online\]. Available: <http://eur-lex.europa.eu/eli/reg/com/2008/1205>                                                       |
| \[INSPIRE-MD-TG\]   | European Commission, “INSPIRE Metadata Implementing Rules: Technical Guidelines based on EN ISO 19115 and EN ISO 19119,” 2013. \[Online\]. Available: <http://inspire.ec.europa.eu/index.cfm/pageid/101>                                                                                                                  |
| \[INSPIRE-MT\]      | European Commission, “INSPIRE Media Type Register,” \[Online\]. Available: <http://inspire.ec.europa.eu/media-types/>                                                                                                                                                                                                     |
| \[ISO19115\]        | ISO (International Organization for Standardization), “ISO 19115:2003 Geographic information -- Metadata,” 2003. \[Online\]. Available: <http://www.iso.org/iso/catalogue_detail?csnumber=26020>                                                                                                                          |
| \[ISO19115-1\]      | ISO (International Organization for Standardization), “ISO 19115-1:2014 -- Geographic information -- Metadata -- Part 1: Fundamentals,” 2014. \[Online\]. Available: <http://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=53798>                                                              |
| \[ISO19119\]        | ISO (International Organization for Standardization), “ISO 19119:2005 -- Geographic information -- Services,” 2005. \[Online\]. Available: <http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=39890>                                                                                           |
| \[ISO19125-1\]      | ISO (International Organization for Standardization), “ISO 19125-1:2004 Geographic information -- Simple feature access -- Part 1: Common architecture,” 2004. \[Online\]. Available: <http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=40114>                                                |
| \[ISO19139\]        | ISO (International Organization for Standardization), “ISO/TS 19139:2007 - Geographic information -- Metadata -- XML schema implementation,” 2007. \[Online\]. Available: <http://www.iso.org/iso/catalogue_detail.htm?csnumber=32557>                                                                                    |
| \[ISO639-2\]        | ISO (International Organization for Standardization), “ISO 639-2:1998 Codes for the representation of names of languages -- Part 2: Alpha-3 code,” 1998. \[Online\]. Available: <http://www.iso.org/iso/catalogue_detail?csnumber=4767>                                                                                   |
| \[KML\]             | Open Geospatial Consortium, “Keyhole Markup Language (KML),” \[Online\]. Available: <http://www.opengeospatial.org/standards/kml>                                                                                                                                                                                         |
| \[LAT-LONG\]        | W3C, “WGS84 Geo Positioning: an RDF vocabulary,” 2009. \[Online\]. Available: [http://www.w3.org/2003/01/geo/wgs84\_pos\#](http://www.w3.org/2003/01/geo/wgs84_pos)                                                                                                                                                       |
| \[LOCN\]            | European Commission, ISA Programme, “ISA Programme Location Core Vocabulary,” 2015. \[Online\]. Available: [http://www.w3.org/ns/locn\#](http://www.w3.org/ns/locn)                                                                                                                                                       |
| \[MDR-CONT\]        | Publications Office of the EU, “Named Authority List: Continents,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/continent/>                                                                                                                                                                        |
| \[MDR-COUNTRIES\]   | Publications Office of the EU, “Named Authority List: Countries,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/country/>                                                                                                                                                                           |
| \[MDR-FREQ\]        | Publications Office of the EU, “Named Authority List: Frequencies,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/frequency/>                                                                                                                                                                       |
| \[MDR-FT\]          | Publications Office of the EU, “Named Authority List: File Types,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/file-type/>                                                                                                                                                                        |
| \[MDR-LANG\]        | Publications Office of the EU, “Named Authority List: Languages,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/language/>                                                                                                                                                                          |
| \[MDR-PLACES\]      | Publications Office of the EU, “Named Authority List: Places,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/place/>                                                                                                                                                                                |
| \[MDR-THEMES\]      | Publications Office of the EU, “Named Authority List: Data Themes,” \[Online\]. Available: <http://publications.europa.eu/mdr/authority/data-theme/>                                                                                                                                                                      |
| \[NEOGEO\]          | GeoVocab.org, “NeoGeo Vocabulary Specification - Madrid Edition,” 2012. \[Online\]. Available: <http://geovocab.org/doc/neogeo/>                                                                                                                                                                                          |
| \[PROV\]            | W3C, “PROV-O: The PROV Ontology,” 2013. \[Online\]. Available: <http://www.w3.org/TR/prov-o/>                                                                                                                                                                                                                             |
| \[RFC4288\]         | IETF, “RFC 4288 – Media Type Specifications and Registration Procedures,” 2005. \[Online\]. Available: <https://tools.ietf.org/html/rfc4288>                                                                                                                                                                              |
| \[RFC5870\]         | IETF, “RFC 5870 - A Uniform Resource Identifier for Geographic Locations ('geo' URI),” 2010. \[Online\]. Available: <https://tools.ietf.org/html/rfc5870>                                                                                                                                                                 |
| \[SCHEMA\]          | “Schema.org,” \[Online\]. Available: <http://schema.org>                                                                                                                                                                                                                                                                  |
| \[VCARD\]           | W3C, “vCard Ontology for describing persons and organisations,” 2013. \[Online\]. Available: <http://www.w3.org/TR/vcard-rdf/>                                                                                                                                                                                            |
| \[XML\]             | W3C, “Extensible Markup Language (XML) 1.0 (Fifth Edition),” \[Online\]. Available: <http://www.w3.org/TR/2008/REC-xml-20081126/>                                                                                                                                                                                         |

<span id="_Ref422234659" class="anchor"><span id="_Toc437955423" class="anchor"><span id="_Toc447881041" class="anchor"></span></span></span>Overview of metadata elements covered by GeoDCAT-AP
================================================================================================================================================================================================

The following table provides an overview of the metadata elements in the INSPIRE metadata schema and in the core profile of ISO 19115, and the available mappings in DCAT-AP and GeoDCAT-AP. Columns titled with “obligation” specify whether the corresponding metadata elements are mandatory (M), conditional (C), and optional (O) (where “conditional” means “mandatory under given conditions”).

Note that the mappings covered by DCAT-AP correspond to those defined in GeoDCAT-AP *core*, whereas those covered only by GeoDCAT-AP correspond to those defined in the GeoDCAT-AP *extended*.

<span id="_Toc437955460" class="anchor"><span id="_Toc447881079" class="anchor"></span></span>Table : Overview of covered metadata elements

| INSPIRE                                                             | Obligation | ISO 19115 Core                                                                       | Obligation | DCAT-AP                                                              | GeoDCAT-AP                                        |
|---------------------------------------------------------------------|------------|--------------------------------------------------------------------------------------|------------|----------------------------------------------------------------------|---------------------------------------------------|
| Metadata point of contact                                           | M          | Metadata point of contact                                                            | M          |                                                                      | Yes                                               |
| Metadata date                                                       | M          | Metadata date stamp                                                                  | M          | Yes                                                                  | Yes                                               |
| Metadata language                                                   | M          | Metadata language                                                                    | C          | Yes                                                                  | Yes                                               |
|                                                                     |            | Metadata character set                                                               | C          |                                                                      | Yes                                               |
|                                                                     |            | Metadata file identifier                                                             | O          |                                                                      | Yes                                               |
|                                                                     |            | Metadata standard name                                                               | O          |                                                                      | Yes                                               |
|                                                                     |            | Metadata standard version                                                            | O          |                                                                      | Yes                                               |
| Resource title                                                      | M          | Dataset title                                                                        | M          | Yes                                                                  | Yes                                               |
| Temporal reference - Date of creation / publication / last revision | C          | Dataset reference date                                                               | M          | Partially (creation date not included)                               | Yes                                               |
| Resource abstract                                                   | M          | Abstract describing the dataset                                                      | M          | Yes                                                                  | Yes                                               |
| Resource language                                                   | C          | Dataset language                                                                     | M          | Yes                                                                  | Yes                                               |
| Topic category                                                      | M          | Dataset topic category                                                               | M          |                                                                      | Yes                                               |
| Geographic bounding box                                             | M          | Geographic location of the dataset (by four coordinates or by geographic identifier) | C          | Yes                                                                  | Yes                                               |
| Character encoding                                                  | C          | Dataset character set                                                                | C          |                                                                      | Yes                                               |
| Temporal reference - Temporal extent                                | C          | Additional extent information for the dataset (vertical and temporal)                | O          | Partially (temporal extent only)                                     | Partially (temporal extent only)                  |
| Lineage                                                             | M          | Lineage                                                                              | O          | Yes                                                                  | Yes                                               |
| Spatial representation type                                         | M          | Spatial representation type                                                          | O          |                                                                      | Yes                                               |
| Encoding                                                            | M          | Distribution format                                                                  | O          | Yes                                                                  | Yes                                               |
| Spatial resolution                                                  | C          | Spatial resolution of the dataset                                                    | O          |                                                                      | Yes (but as free text)                            |
| Responsible organisation                                            | M          | Dataset responsible party                                                            | O          | Partially (only 3 of the 11 responsible party roles are supported)   | Yes                                               |
| Resource locator                                                    | C          | On-line resource                                                                     | O          | Yes                                                                  | Yes                                               |
| Coordinate reference system; Temporal reference system              | M; C       | Reference system                                                                     | O          |                                                                      | Yes                                               |
| Conformity                                                          | M          |                                                                                      |            | Yes                                                                  | Yes                                               |
| Resource type                                                       | M          |                                                                                      |            | Partially (only datasets, series and discovery / catalogue services) | Yes                                               |
| Spatial data service type                                           | M          |                                                                                      |            |                                                                      | Yes                                               |
| Keyword                                                             | M          |                                                                                      |            | Partially (only for datasets and dataset series)                     | Yes                                               |
| Coupled resource                                                    | C          |                                                                                      |            |                                                                      | Yes                                               |
| Unique resource identifier                                          | M          |                                                                                      |            | Yes                                                                  | Yes                                               |
| Conditions for access and use                                       | M          |                                                                                      |            | Yes                                                                  | Yes                                               |
| Limitations on public access                                        | M          |                                                                                      |            | Yes                                                                  | Yes                                               |
| Maintenance information                                             | O          |                                                                                      |            | Partially (only maintenance and update frequency)                    | Partially (only maintenance and update frequency) |
| Data quality – Logical consistency – Topological consistency        | C          |                                                                                      |            |                                                                      | Partially (only conformance results)              |
| Data quality – Logical consistency – Conceptual consistency         | O          |                                                                                      |            |                                                                      | Partially (only conformance results)              |
| Data quality – Logical consistency – Domain consistency             | O          |                                                                                      |            |                                                                      | Partially (only conformance results)              |

<span id="_Ref424148624" class="anchor"><span id="_Toc437955424" class="anchor"><span id="_Toc447881042" class="anchor"></span></span></span>Detailed usage notes and examples
==============================================================================================================================================================================

This annex contains further usage notes and examples on the mappings summarised in Section 5 of the GeoDCAT-AP specification.

<span id="_Toc414637482" class="anchor"><span id="_Ref416757124" class="anchor"><span id="_Toc437955425" class="anchor"><span id="_Ref438646950" class="anchor"><span id="_Toc447881043" class="anchor"></span></span></span></span></span>Resource title - \*Dataset title 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The content of the element ‘resource title’ can be represented in RDF as a plain literal, and by using property dct:title.

This binding may also include the specification of the language by using attribute @xml:lang \[XML\]. The language to be specified is the one indicated by element metadata language, mapped to the language identifiers defined by IETF BCP 47 \[BCP47\].

| Example                                           |
|---------------------------------------------------|
| *\# Resource metadata in GeoDCAT-AP*              
                                                    
 \[\] dct:title "Forest / Non-Forest Map 2006"@en.  |
| &lt;!-- Resource metadata in ISO19139 --&gt;      
                                                    
 &lt;gmd:MD\_Metadata …                             
                                                    
 ...                                                
                                                    
 &lt;gmd:identificationInfo&gt;                     
                                                    
 &lt;gmd:MD\_DataIdentification&gt;                 
                                                    
 &lt;gmd:citation&gt;                               
                                                    
 &lt;gmd:CI\_Citation&gt;                           
                                                    
 &lt;gmd:title&gt;                                  
                                                    
 &lt;gco:CharacterString&gt;                        
                                                    
 Forest / Non-Forest Map 2006                       
                                                    
 &lt;/gco:CharacterString&gt;                       
                                                    
 &lt;/gmd:title&gt;                                 
                                                    
 &lt;/gmd:CI\_Citation&gt;                          
                                                    
 &lt;/gmd:citation&gt;                              
                                                    
 &lt;/gmd:MD\_DataIdentification&gt;                
                                                    
 &lt;/gmd:identificationInfo&gt;                    
                                                    
 ...                                                
                                                    
 &lt;/gmd:MD\_Metadata&gt;                          |

<span id="_Toc414637483" class="anchor"><span id="_Ref416757177" class="anchor"><span id="_Toc437955426" class="anchor"><span id="_Ref438646961" class="anchor"><span id="_Toc447881044" class="anchor"></span></span></span></span></span>Resource abstract - \*Abstract describing the dataset
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The content of the elements ‘resource abstract’ can be represented in RDF as a plain literal, and by using property dct:description.

This binding may also include the specification of the language by using attribute @xml:lang \[XML\]. The language to be specified is the one indicated by element metadata language, mapped to the language identifiers defined by IETF BCP 47 \[BCP47\].

| Example                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 \[\] dct:description "Pan-European Forest / Non Forest Map with target year 2006, Data Source: Landsat ETM+ and Corine Land Cover 2006, Classes: for-est, non-forest, clouds/snow, no data; Method: automatic classification performed with an in-house algorithm; spatial resolution: 25m. In addition, the forest map 2006 is extended to FTYPE2006 to include forest types (broadleaf, coniferous forest) that are mapped using MODIS composites."@en .  |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;gmd:MD\_Metadata …                                                                                                                                                                                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 ...                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;gmd:identificationInfo&gt;                                                                                                                                                                                                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;gmd:MD\_DataIdentification&gt;                                                                                                                                                                                                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;gmd:abstract&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;gco:CharacterString&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 Pan-European Forest / Non Forest Map with target year 2006, Data Source: Landsat ETM+ and Corine Land Cover 2006, Classes: for-est, non-forest, clouds/snow, no data; Method: automatic classification performed with an in-house algorithm; spatial resolution: 25m. In addition, the forest map 2006 is extended to FTYPE2006 to include forest types (broadleaf, coniferous forest) that are mapped using MODIS composites.                              
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;/gco:CharacterString&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;/gmd:abstract&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;/gmd:MD\_DataIdentification&gt;                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;/gmd:identificationInfo&gt;                                                                                                                                                                                                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 ...                                                                                                                                                                                                                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                                                                                                                                                                                                             
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                                                                                                                                                                                                                                                   |

<span id="_Toc414637484" class="anchor"><span id="_Ref415120018" class="anchor"><span id="_Ref416757140" class="anchor"><span id="_Ref416757164" class="anchor"><span id="_Ref417894587" class="anchor"><span id="_Ref420942592" class="anchor"><span id="_Toc437955427" class="anchor"><span id="_Ref438646973" class="anchor"><span id="_Ref438647071" class="anchor"><span id="_Ref438647262" class="anchor"><span id="_Ref438648168" class="anchor"><span id="_Ref438648262" class="anchor"><span id="_Toc447881045" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span></span>Resource type - \*not in ISO 19115 core
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In \[DCAT\], the notion of dataset is quite broad, and may include both the INSPIRE notions of **dataset** and **dataset series**. Moreover, currently no existing vocabulary provides suitable candidates for the INSPIRE notions of dataset series – the existing ones are very generic (e.g., dctype:Collection is defined as "An aggregation of resources" \[DCTERMS\]).

Based on this, in GeoDCAT-AP both INSPIRE datasets and dataset series are specified as instances of dcat:Dataset.

Moreover, in order to maintain the INSPIRE distinction between datasets and dataset series, following the work on aligning INSPIRE Metadata and Dublin Core \[INSPIRE-DC\], in the extended profile of GeoDCAT-AP they will be denoted by using the resource type code list operated by the INSPIRE Registry, and by using dct:type. More precisely, the following URIs should be used to denote, respectively, dataset and series:

-   <http://inspire.ec.europa.eu/metadata-codelist/ResourceType/dataset>

-   <http://inspire.ec.europa.eu/metadata-codelist/ResourceType/series>

As far as the INSPIRE notion of **service** is concerned, DCAT and DCAT-AP foresee a single class, namely, dcat:Catalog, which only matches the notion of ‘discovery service’ in INSPIRE. Other services will be of type dctype:Service. Additionally, the spatial data service type can be specified by using dct:type with the corresponding code lists operated by the INSPIRE Registry. More precisely, the following URI should be used to denote services:

-   <http://inspire.ec.europa.eu/metadata-codelist/ResourceType/service>

For the reason explained above, the core profile of GeoDCAT-AP includes only the mappings for catalogue services (i.e., dcat:Catalog), whereas the mappings of other types of services are supported only in the extended profile of GeoDCAT-AP

| Example                                                                                                                                                                   |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                        
                                                                                                                                                                            
 \#\# Resource type for datasets                                                                                                                                            
                                                                                                                                                                            
 \[\] a dcat:Dataset;                                                                                                                                                       
                                                                                                                                                                            
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResourceType/dataset*&gt;                                                                                      
                                                                                                                                                                            
 \#\# Resource type for series                                                                                                                                              
                                                                                                                                                                            
 \[\] a dcat:Dataset;                                                                                                                                                       
                                                                                                                                                                            
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResourceType/series*&gt;                                                                                       
                                                                                                                                                                            
 \#\# Resource type for services (here, a view service)                                                                                                                     
                                                                                                                                                                            
 \[\] a dctype:Service;                                                                                                                                                     
                                                                                                                                                                            
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResourceType/service*&gt; ,                                                                                    
                                                                                                                                                                            
 &lt;*http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType/view*&gt; .                                                                                      |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                              
                                                                                                                                                                            
 &lt;!-- MD\_ScopeCode for a dataset in ISO19139 --&gt;                                                                                                                     
                                                                                                                                                                            
 &lt;gmd:MD\_Metadata …                                                                                                                                                     
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;gmd:hierarchyLevel&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;gmd:MD\_ScopeCode                                                                                                                                                      
                                                                                                                                                                            
 codeList=" *http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/gmxCodelists.xml\#MD\_ScopeCode*" codeListValue="dataset"&gt;  
                                                                                                                                                                            
 dataset                                                                                                                                                                    
                                                                                                                                                                            
 &lt;/gmd:MD\_ScopeCode&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;/gmd:hierarchyLevel&gt;                                                                                                                                                
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                  
                                                                                                                                                                            
 &lt;!-- MD\_ScopeCode for a data series in ISO19139 --&gt;                                                                                                                 
                                                                                                                                                                            
 &lt;gmd:MD\_Metadata …                                                                                                                                                     
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;gmd:hierarchyLevel&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;gmd:MD\_ScopeCode                                                                                                                                                      
                                                                                                                                                                            
 codeList=" *http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/gmxCodelists.xml\#MD\_ScopeCode*" codeListValue="series"&gt;   
                                                                                                                                                                            
 series                                                                                                                                                                     
                                                                                                                                                                            
 &lt;/gmd:MD\_ScopeCode&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;/gmd:hierarchyLevel&gt;                                                                                                                                                
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                  
                                                                                                                                                                            
 &lt;!-- MD\_ScopeCode for a service in ISO19139 --&gt;                                                                                                                     
                                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                   
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;gmd:hierarchyLevel&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;gmd:MD\_ScopeCode                                                                                                                                                      
                                                                                                                                                                            
 codeList=" *http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/gmxCodelists.xml\#MD\_ScopeCode*" codeListValue="service"&gt;  
                                                                                                                                                                            
 service                                                                                                                                                                    
                                                                                                                                                                            
 &lt;/gmd:MD\_ScopeCode&gt;                                                                                                                                                 
                                                                                                                                                                            
 &lt;/gmd:hierarchyLevel&gt;                                                                                                                                                
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;srv:SV\_ServiceIdentification&gt;                                                                                                                                      
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;srv:serviceType&gt;                                                                                                                                                    
                                                                                                                                                                            
 &lt;gco:LocalName&gt;view&lt;/gco:LocalName&gt;                                                                                                                            
                                                                                                                                                                            
 &lt;/srv:serviceType&gt;                                                                                                                                                   
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;/srv:SV\_ServiceIdentification&gt;                                                                                                                                     
                                                                                                                                                                            
 ...                                                                                                                                                                        
                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                  |

<span id="_Toc414637485" class="anchor"><span id="_Ref416757252" class="anchor"><span id="_Toc437955428" class="anchor"><span id="_Ref438647082" class="anchor"><span id="_Ref438647096" class="anchor"><span id="_Ref438647107" class="anchor"><span id="_Ref438647116" class="anchor"><span id="_Ref438647126" class="anchor"><span id="_Ref438647137" class="anchor"><span id="_Ref438647153" class="anchor"><span id="_Ref438647163" class="anchor"><span id="_Toc447881046" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span>Resource locator - \*On-line resource
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In INSPIRE, this element, quoting, “defines the link(s) to the resource and/or the link to additional information about the resource”.

For datasets, \[DCAT\] foresees a property, namely, dcat:landingPage, having exactly the same purpose. By contrast, the only property foreseen in DCAT for linking a service to an online resource is foaf:homepage.

ISO 19115 offers however the ability to specify the “type” of resource locator by using a specific code list (CI\_OnlineFunctionCode), described in the following table:

| ISO 19115 – CI\_OnlineFunctionCode | Description                                                                            |
|------------------------------------|----------------------------------------------------------------------------------------|
| download                           | online instructions for transferring data from one storage device or system to another |
| information                        | online information about the resource                                                  |
| offlineAccess                      | online instructions for requesting the resource from the provider                      |
| order                              | online order process for obtaining the resource                                        |
| search                             | online search interface for seeking out information about the resource                 |

Based on this, the mappings of element “resource locator” are the following:

-   foaf:homepage for services;

-   for data sets and data set series, the mapping will vary depending on the function code (when available), based on the following table.

| ISO 19115 – CI\_OnlineFunctionCode | Property         | Domain            | Range         |
|------------------------------------|------------------|-------------------|---------------|
| (not provided)                     | dcat:landingPage | dcat:Dataset      | foaf:Document |
| download                           | dcat:accessURL   | dcat:Distribution | rdfs:Resource |
| Information                        | foaf:page        | dcat:Dataset      | foaf:Document |
| offlineAccess                      | dcat:accessURL   | dcat:Distribution | rdfs:Resource |
| order                              | dcat:accessURL   | dcat:Distribution | rdfs:Resource |
| search                             | foaf:page        | dcat:Dataset      | foaf:Document |

| Example                                                                                                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 \#\# Resource locator for datasets and series                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                   
 \[\] a dcat:Dataset;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 foaf:page &lt;*http://forest.jrc.ec.europa.eu/forestmap-download*&gt;                                                                                                                                                                                             
                                                                                                                                                                                                                                                                   
 \#\# Resource locator for services                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                   
 \[\] a dcat:Catalog; foaf:homepage &lt;*http://geohub.jrc.ec.europa.eu/efas\_cc?service=WMS&request=GetCapabilities*&gt; .                                                                                                                                        |
| &lt;!-- Resource metadata in ISO19139 for datasets --&gt;                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                   
 &lt;gmd:MD\_Metadata …                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:transferOptions&gt;                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                   
 &lt;gmd:MD\_DigitalTransferOptions&gt;                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                   
 &lt;gmd:onLine&gt;                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                   
 &lt;gmd:CI\_OnlineResource&gt;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                   
 &lt;gmd:linkage&gt;                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:URL&gt; *http://forest.jrc.ec.europa.eu/forestmap-download* &lt;/gmd:URL&gt;                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 &lt;/gmd:linkage&gt;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 &lt;gmd:name&gt;                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                                   
 &lt;gco:CharacterString&gt; … &lt;/gco:CharacterString&gt;                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                   
 &lt;/gmd:name&gt;                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                   
 &lt;gmd:description&gt;                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                   
 &lt;gco:CharacterString&gt; … &lt;/gco:CharacterString&gt;                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                   
 &lt;/gmd:description&gt;                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                   
 &lt;gmd:function&gt;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 &lt;CI\_OnLineFunctionCode codeListValue="information" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_OnLineFunctionCode*" xmlns="*http://www.isotc211.org/2005/gmd*"/&gt;  
                                                                                                                                                                                                                                                                   
 &lt;/gmd:function&gt;                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                   
 &lt;/gmd:CI\_OnlineResource&gt;                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                   
 &lt;/gmd:onLine&gt;                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;/gmd:MD\_DigitalTransferOptions&gt;                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                   
 &lt;/gmd:transferOptions&gt;                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                   
 &lt;!-- Resource locator in ISO19139 for services --&gt;                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                   
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:distributionInfo&gt;                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                   
 &lt;gmd:MD\_Distribution&gt;                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:transferOptions&gt;                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                   
 &lt;gmd:MD\_DigitalTransferOptions&gt;                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                   
 &lt;gmd:onLine&gt;                                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                                   
 &lt;gmd:CI\_OnlineResource&gt;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:linkage&gt;                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;gmd:URL&gt;*http://geohub.jrc.ec.europa.eu/efas\_cc?service=WMS&request=GetCapabilities*&lt;/gmd:URL&gt;                                                                                                                                                      
                                                                                                                                                                                                                                                                   
 &lt;/gmd:linkage&gt;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 &lt;gmd:function&gt;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                   
 &lt;CI\_OnLineFunctionCode codeListValue="information" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_OnLineFunctionCode*" xmlns="*http://www.isotc211.org/2005/gmd*"/&gt;  
                                                                                                                                                                                                                                                                   
 &lt;/gmd:function&gt;                                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;/gmd:CI\_OnlineResource&gt;                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                   
 &lt;/gmd:onLine&gt;                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;/gmd:MD\_DigitalTransferOptions&gt;                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                   
 &lt;/gmd:transferOptions&gt;                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                   
 &lt;/gmd:MD\_Distribution&gt;                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                   
 &lt;/gmd:distributionInfo&gt;                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                                   
 ...                                                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                                   
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                                                         |

<span id="_Toc414637486" class="anchor"><span id="_Ref416757265" class="anchor"><span id="_Ref417901510" class="anchor"><span id="_Toc437955429" class="anchor"><span id="_Ref438647176" class="anchor"><span id="_Toc447881047" class="anchor"></span></span></span></span></span></span>Unique resource identifier - \*not in ISO 19115 core
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In INSPIRE, this element is meant to uniquely identify a resource (dataset, series or service), and it is mandatory for datasets and series. It is specified by (a) a *mandatory* character string code and by (b) an *optional* character string namespace.

Based on DCAT-AP, unique resource identifiers are mapped to dct:identifier (see the following example). The actual value is obtained by the concatenation of the values of the namespace (if specified) and of the code in the original metadata record.

| Example                                                      |
|--------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                           
                                                               
 \[\] dct:identifier "12345"^^xsd:string .                     |
| &lt;!-- Resource metadata in ISO19139 --&gt;                 
                                                               
 &lt;gmd:MD\_Metadata&gt;                                      
                                                               
 ...                                                           
                                                               
 &lt;gmd:identificationInfo&gt;                                
                                                               
 &lt;gmd:MD\_DataIdentification&gt;                            
                                                               
 ...                                                           
                                                               
 &lt;gmd:identifier&gt;                                        
                                                               
 &lt;gmd:MD\_Identifier&gt;                                    
                                                               
 &lt;gmd:code&gt;                                              
                                                               
 &lt;gco:CharacterString&gt;12345&lt;/gco:CharacterString&gt;  
                                                               
 &lt;/gmd:code&gt;                                             
                                                               
 &lt;/gmd:MD\_Identifier&gt;                                   
                                                               
 &lt;/gmd:identifier&gt;                                       
                                                               
 &lt;/gmd:MD\_DataIdentification&gt;                           
                                                               
 &lt;/gmd:identificationInfo&gt;                               
                                                               
 ...                                                           
                                                               
 &lt;/gmd:MD\_Metadata&gt;                                     |

If the unique resource identifier is specified with or can be encoded as an HTTP URI, it can be used as the URI of the resource (see the following example).

| Example                                                                     |
|-----------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                          
                                                                              
 &lt;http://some.site/resource/12345&gt;                                      
                                                                              
 dct:identifier "http://some.site/resource/12345"^^xsd:anyURI .               |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                
                                                                              
 &lt;!—Unique resource identifier specified only with code --&gt;             
                                                                              
 &lt;gmd:MD\_Metadata&gt;                                                     
                                                                              
 ...                                                                          
                                                                              
 &lt;gmd:identificationInfo&gt;                                               
                                                                              
 &lt;gmd:MD\_DataIdentification&gt;                                           
                                                                              
 ...                                                                          
                                                                              
 &lt;gmd:identifier&gt;                                                       
                                                                              
 &lt;gmd:MD\_Identifier&gt;                                                   
                                                                              
 &lt;gmd:code&gt;                                                             
                                                                              
 &lt;gco:CharacterString&gt;                                                  
                                                                              
 http://some.site/dataset/12345                                               
                                                                              
 &lt;/gco:CharacterString&gt;                                                 
                                                                              
 &lt;/gmd:code&gt;                                                            
                                                                              
 &lt;/gmd:MD\_Identifier&gt;                                                  
                                                                              
 &lt;/gmd:identifier&gt;                                                      
                                                                              
 &lt;/gmd:MD\_DataIdentification&gt;                                          
                                                                              
 &lt;/gmd:identificationInfo&gt;                                              
                                                                              
 ...                                                                          
                                                                              
 &lt;/gmd:MD\_Metadata&gt;                                                    
                                                                              
 &lt;!-- Unique resource identifier specified with code and namespace --&gt;  
                                                                              
 &lt;gmd:MD\_Metadata&gt;                                                     
                                                                              
 ...                                                                          
                                                                              
 &lt;gmd:identificationInfo&gt;                                               
                                                                              
 &lt;gmd:MD\_DataIdentification&gt;                                           
                                                                              
 ...                                                                          
                                                                              
 &lt;gmd:identifier&gt;                                                       
                                                                              
 &lt;gmd:RS\_Identifier&gt;                                                   
                                                                              
 &lt;gmd:code&gt;                                                             
                                                                              
 &lt;gco:CharacterString&gt;                                                  
                                                                              
 12345                                                                        
                                                                              
 &lt;/gco:CharacterString&gt;                                                 
                                                                              
 &lt;/gmd:code&gt;                                                            
                                                                              
 &lt;gmd:codeSpace&gt;                                                        
                                                                              
 &lt;gco:CharacterString&gt;                                                  
                                                                              
 http://some.site/dataset/                                                    
                                                                              
 &lt;/gco:CharacterString&gt;                                                 
                                                                              
 &lt;/gmd:codeSpace&gt;                                                       
                                                                              
 &lt;/gmd:RS\_Identifier&gt;                                                  
                                                                              
 &lt;/gmd:identifier&gt;                                                      
                                                                              
 &lt;/gmd:MD\_DataIdentification&gt;                                          
                                                                              
 &lt;/gmd:identificationInfo&gt;                                              
                                                                              
 ...                                                                          
                                                                              
 &lt;/gmd:MD\_Metadata&gt;                                                    |

<span id="_Ref416757280" class="anchor"><span id="_Toc437955430" class="anchor"><span id="_Toc447881048" class="anchor"><span id="_Toc414637487" class="anchor"></span></span></span></span>Coupled resource - \*not in ISO 19115 core
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This element is used to link a service to the target datasets or dataset series.

This relationship is modelled by using dct:hasPart. This mapping is supported only in the extended profile of GeoDCAT-AP.

NB: The notion of “coupled resource” does not apply to catalogue / discovery services. As per the DCAT-AP, in GeoDCAT-AP (core and extended profiles) the relationship between the catalogue and the available datasets is modelled by using dcat:dataset, which is a sub-property of dct:hasPart.

The target dataset or series should be preferably referred to by using its unique resource identifier (as in the following example).

| Example                                                                                 |
|-----------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                      
                                                                                          
 \[\] a dctype:Service                                                                    
                                                                                          
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResourceType/service*&gt; ,  
                                                                                          
 &lt;*http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType/view*&gt; ;    
                                                                                          
 dct:hasPart \[                                                                           
                                                                                          
 dct:identifier "12345"^^xsd:string                                                       
                                                                                          
 \] .                                                                                     |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                            
                                                                                          
 &lt;gmd:MD\_Metadata&gt;                                                                 
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;gmd:identificationInfo&gt;                                                           
                                                                                          
 &lt;srv:SV\_ServiceIdentification&gt;                                                    
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;srv:operatesOn&gt;                                                                   
                                                                                          
 &lt;!-- Coupled resource identification (either embedded or by reference) --&gt;         
                                                                                          
 &lt;/srv:operatesOn&gt;                                                                  
                                                                                          
 &lt;/srv:SV\_ServiceIdentification&gt;                                                   
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;/gmd:identificationInfo&gt;                                                          
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;/gmd:MD\_Metadata&gt;                                                                
                                                                                          
 &lt;!-- Coupled resource metadata (data identification section) --&gt;                   
                                                                                          
 &lt;gmd:MD\_Metadata&gt;                                                                 
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;gmd:identificationInfo&gt;                                                           
                                                                                          
 &lt;gmd:MD\_DataIdentification&gt;                                                       
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;gmd:identifier&gt;                                                                   
                                                                                          
 &lt;gmd:MD\_Identifier&gt;                                                               
                                                                                          
 &lt;gmd:code&gt;                                                                         
                                                                                          
 &lt;gco:CharacterString&gt;12345&lt;/gco:CharacterString&gt;                             
                                                                                          
 &lt;/gmd:code&gt;                                                                        
                                                                                          
 &lt;/gmd:MD\_Identifier&gt;                                                              
                                                                                          
 &lt;/gmd:identifier&gt;                                                                  
                                                                                          
 &lt;/gmd:MD\_DataIdentification&gt;                                                      
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;/gmd:identificationInfo&gt;                                                          
                                                                                          
 ...                                                                                      
                                                                                          
 &lt;/gmd:MD\_Metadata&gt;                                                                |

<span id="_Ref415122624" class="anchor"><span id="_Toc437955431" class="anchor"><span id="_Toc447881049" class="anchor"></span></span></span>Resource language and metadata language - \*Dataset language and Metadata language
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In INSPIRE metadata, metadata and resource languages (which may be different) are specified by using the three-letter language codes defined in \[ISO639-2\].

Based on DCAT-AP, both elements are specified with property dct:language, with the URI of the relevant language available from the relevant register operated by the EU Publications Office \[MDR-LANG\].

The following example assumes that the metadata language is Dutch, and the resource language is German.

| Example                                                                                           |
|---------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                
                                                                                                    
 \# Resource metadata                                                                               
                                                                                                    
 \[\] dct:language                                                                                  
                                                                                                    
 &lt;*http://publications.europa.eu/resource/authority/language/DEU*&gt; ;                          
                                                                                                    
 foaf:isPrimaryTopicOf                                                                              
                                                                                                    
 \# Metadata on metadata                                                                            
                                                                                                    
 \[ dct:language                                                                                    
                                                                                                    
 &lt;*http://publications.europa.eu/resource/authority/language/NLD*&gt; \] .                       |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                      
                                                                                                    
 &lt;gmd:MD\_Metadata&gt;                                                                           
                                                                                                    
 ...                                                                                                
                                                                                                    
 &lt;!-- Metadata on metadata: metadata language --&gt;                                             
                                                                                                    
 &lt;gmd:language&gt;                                                                               
                                                                                                    
 &lt;gmd:LanguageCode codeList="*http://www.loc.gov/standards/iso639-2/*" codeListValue="dut"/&gt;  
                                                                                                    
 &lt;/gmd:language&gt;                                                                              
                                                                                                    
 ...                                                                                                
                                                                                                    
 &lt;!-- Resource language --&gt;                                                                   
                                                                                                    
 &lt;gmd:identificationInfo&gt;                                                                     
                                                                                                    
 &lt;gmd:MD\_DataIdentification&gt;                                                                 
                                                                                                    
 ...                                                                                                
                                                                                                    
 &lt;gmd:language&gt;                                                                               
                                                                                                    
 &lt;gmd:LanguageCode codeList="*http://www.loc.gov/standards/iso639-2/*" codeListValue="ger"/&gt;  
                                                                                                    
 &lt;/gmd:language&gt;                                                                              
                                                                                                    
 ...                                                                                                
                                                                                                    
 &lt;/gmd:MD\_DataIdentification&gt;                                                                
                                                                                                    
 &lt;/gmd:identificationInfo&gt;                                                                    
                                                                                                    
 ...                                                                                                
                                                                                                    
 &lt;/gmd:MD\_Metadata&gt;                                                                          |

The metadata language can be also used to specify the language of textual elements of resource metadata by using the @xml:lang attribute \[XML\].

Since @xml:lang takes as value language identifiers defined by IETF BCP 47 \[BCP47\], a mapping from the actual value of the metadata language is needed.

<span id="_Toc414637488" class="anchor"><span id="_Ref416757329" class="anchor"><span id="_Ref419315262" class="anchor"><span id="_Toc437955432" class="anchor"><span id="_Ref438647890" class="anchor"><span id="_Ref438648198" class="anchor"><span id="_Ref438648274" class="anchor"><span id="_Ref438648332" class="anchor"><span id="_Ref438648584" class="anchor"><span id="_Toc447881050" class="anchor"></span></span></span></span></span></span></span></span></span></span>Topic category, originating controlled vocabulary, and keyword value - \*Dataset topic category
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In INSPIRE, these two elements have specific purposes. Quoting from the INSPIRE Metadata Regulation \[INSPIRE-MD-REG\] ([§2.1](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e233-14-1) and [§3.1](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e233-14-1), respectively):

-   The topic category is a high-level classification scheme to assist in the grouping and topic-based search of available spatial data resources.

-   The keyword value is a commonly used word, formalised word or phrase used to describe the subject. While the topic category is too coarse for detailed queries, keywords help narrowing a full text search and they allow for structured keyword search.

Moreover, two types of keywords are allowed:

-   free keywords;

-   keywords taken from a controlled vocabulary.

Finally, topic categories apply only to datasets and dataset series.

### Topic category and keyword in datasets and dataset series

As far as dataset metadata are concerned, in both DCAT and DCAT-AP, a distinction is made only between free keywords and keywords from controlled vocabularies, associated with a URI. For the former, dcat:keyword is used, whereas for the latter dcat:theme (which is a sub-property of dct:subject). Since the INSPIRE Registry operates URI registers for topic categories and INSPIRE spatial data themes, and in order to keep the distinction existing in INSPIRE between topic categories and keywords, the mapping is as follows:

-   Topic category is mapped to dct:subject, and expressed by the corresponding URIs minted for the ISO code list in the INSPIRE Registry – reference register:

    -   <http://inspire.ec.europa.eu/metadata-codelist/TopicCategory>

-   Keywords not associated with a controlled vocabulary will be mapped to dcat:keyword;

-   INSPIRE spatial data themes are mapped to dcat:theme and expressed by the corresponding URI in the INSPIRE Registry – reference register:

-   <http://inspire.ec.europa.eu/theme>

-   Keywords associated with other controlled vocabularies are mapped to dcat:theme.

Following DCAT-AP recommendations, keywords from controlled vocabularies should be preferably specified with dereferenceable HTTP URIs. In such a case, the information concerning the originating controlled vocabulary can be omitted.

When keywords cannot be specified with HTTP URIs, they should be modelled as a skos:Concept associated with a skos:ConceptScheme (modelling the originating controlled vocabulary), and annotated with the textual content and reference date(s) in the relevant INSPIRE metadata elements.

The representation of the information concerning the controlled vocabulary is illustrated in the following table.

<span id="_Toc437955461" class="anchor"><span id="_Toc447881080" class="anchor"></span></span>Table : Mappings for metadata element ‘originating controlled vocabulary’

| Metadata Element                  | Proposed mapping |
|-----------------------------------|------------------|
| Originating controlled vocabulary | Title            |
|                                   | Reference date   |
|                                   |                  |
|                                   |                  |

For conformance with DCAT-AP, GeoDCAT-AP records must also include keywords from the MDR Data Theme Named Authority List \[MDR-THEMES\].

In order to ensure consistency, the relevant MDR Data Theme keywords should be selected based on mappings with the controlled vocabularies used in INSPIRE / ISO 19115 metadata.

At the date of publication of this specification, work is under-way to define a set of harmonised mappings between the relevant vocabularies. The status of this work, and links to a machine readable representation of the mappings, is documented on the dedicated page on Joinup, available at:

<https://joinup.ec.europa.eu/node/148245/>

### <span id="_Ref438648297" class="anchor"><span id="_Toc447881052" class="anchor"></span></span>Keyword in services

As far as service metadata are concerned, keywords can classify either a service or the datasets / series operated by the service itself. For the latter, INSPIRE Metadata Regulation requires using at least one of the keywords from the ISO 19119 code list of spatial data service categories.

Both DCAT and DCAT-AP do not foresee any specific property for keywords classifying either a service or the datasets / series operated by a service. Moreover, dcat:theme and dcat:keyword cannot be used for services, since their domain is restricted to dcat:Dataset.

In order to keep the distinction between these two types of keywords, the proposed solution is as follows:

-   Keywords from the ISO 19119 codelists of spatial data service type and categories are mapped to dct:type, and expressed by the corresponding URI in the INSPIRE Registry – reference registers:

    -   <http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType>

    -   <http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory>

-   Keywords not associated with a controlled vocabulary will be mapped to dc:subject, and represented as un-typed literals;

-   INSPIRE spatial data themes are mapped to dct:subject, and expressed by the corresponding URI in the INSPIRE Registry – reference register:

    -   <http://inspire.ec.europa.eu/theme>

-   Keywords associated with other controlled vocabularies are mapped to dct:subject. If not denoted by an HTTP URI, they should be expressed as a skos:Concept associated with a skos:ConceptScheme, and annotated with the textual content and reference date(s) in the relevant INSPIRE metadata elements.

| Example                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                        
                                                                                                                                                            
 \#\# Datasets and series                                                                                                                                   
                                                                                                                                                            
 \[\] a dcat:Dataset ;                                                                                                                                      
                                                                                                                                                            
 \#\#\# Free keywords                                                                                                                                       
                                                                                                                                                            
 dcat:keyword "CHM"@en, "RDSI"@en ;                                                                                                                         
                                                                                                                                                            
 \#\#\# Keywords from controlled vocabularies                                                                                                               
                                                                                                                                                            
 dcat:theme                                                                                                                                                 
                                                                                                                                                            
 \#\#\# Data themes Name Authority List (Environment)                                                                                                       
                                                                                                                                                            
 &lt;*http://publications.europa.eu/resource/authority/data-theme/ENVI*&gt; ,                                                                               
                                                                                                                                                            
 \#\#\# INSPIRE theme URI (land coverage)                                                                                                                   
                                                                                                                                                            
 &lt;*http://inspire.ec.europa.eu/theme/lc*&gt; ,                                                                                                           
                                                                                                                                                            
 \#\#\# Other controlled vocabulary \[ a skos:Concept ;                                                                                                     
                                                                                                                                                            
 skos:prefLabel "coniferous forest"@en ;                                                                                                                    
                                                                                                                                                            
 skos:inScheme \[ a skos:ConceptScheme ;                                                                                                                    
                                                                                                                                                            
 rdfs:label "GEMET - Concepts, version 2.4"@en ;                                                                                                            
                                                                                                                                                            
 dct:issued "2010-01-13"^^xsd:date \] \] ;                                                                                                                  
                                                                                                                                                            
 \#\#\# Topic categories                                                                                                                                    
                                                                                                                                                            
 dct:subject &lt;*http://inspire.ec.europa.eu/metadata-codelist/TopicCategory/geoscientificInformation*&gt; .                                               
                                                                                                                                                            
 \#\# Services                                                                                                                                              
                                                                                                                                                            
 \[\] a dcat:Catalog ;                                                                                                                                      
                                                                                                                                                            
 \#\#\# Free keywords                                                                                                                                       
                                                                                                                                                            
 dc:subject "hydrography"@en ;                                                                                                                              
                                                                                                                                                            
 \#\#\# Keyword from ISO 19119 codelist of spatial data service categories                                                                                  
                                                                                                                                                            
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory/humanGeographicViewer*&gt; ;                                        
                                                                                                                                                            
 \#\#\# Keywords from controlled vocabularies                                                                                                               
                                                                                                                                                            
 dct:subject &lt;*http://inspire.ec.europa.eu/theme/hy*&gt; ,                                                                                               
                                                                                                                                                            
 \[ a skos:Concept ;                                                                                                                                        
                                                                                                                                                            
 skos:prefLabel "Floods"@en ;                                                                                                                               
                                                                                                                                                            
 skos:inScheme \[ a skos:ConceptScheme ;                                                                                                                    
                                                                                                                                                            
 rdfs:label "GEOSS - Societal Benefit Areas, version 1.0"@en ;                                                                                              
                                                                                                                                                            
 dct:issued "2010-08-25"^^xsd:date \] \] .                                                                                                                  |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                              
                                                                                                                                                            
 &lt;!-- Datasets and series --&gt;                                                                                                                         
                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                   
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;gmd:identificationInfo&gt;                                                                                                                             
                                                                                                                                                            
 &lt;gmd:MD\_DataIdentification&gt;                                                                                                                         
                                                                                                                                                            
 &lt;!-- free keywords --&gt;                                                                                                                               
                                                                                                                                                            
 &lt;gmd:descriptiveKeywords&gt;                                                                                                                            
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;CHM&lt;/gco:CharacterString&gt;                                                                                                 
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;RDSI&lt;/gco:CharacterString&gt;                                                                                                
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;/gmd:descriptiveKeywords&gt;                                                                                                                           
                                                                                                                                                            
 &lt;!-- Keywords from controlled vocabularies --&gt;                                                                                                       
                                                                                                                                                            
 &lt;gmd:descriptiveKeywords&gt;                                                                                                                            
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;coniferous forest&lt;/gco:CharacterString&gt;                                                                                   
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:thesaurusName&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;gmd:CI\_Citation&gt;                                                                                                                                   
                                                                                                                                                            
 &lt;gmd:title&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gco:CharacterString&gt;GEMET - Concepts, version 2.4&lt;/gco:CharacterString&gt;                                                                       
                                                                                                                                                            
 &lt;/gmd:title&gt;                                                                                                                                         
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gmd:CI\_Date&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gco:Date&gt;2010-01-13&lt;/gco:Date&gt;                                                                                                                
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gmd:dateType&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:CI\_DateTypeCode                                                                                                                                   
                                                                                                                                                            
 codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_DateTypeCode*"        
                                                                                                                                                            
 codeListValue="publication"&gt;publication&lt;/gmd:CI\_DateTypeCode&gt;                                                                                    
                                                                                                                                                            
 &lt;/gmd:dateType&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:CI\_Date&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;/gmd:CI\_Citation&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;/gmd:thesaurusName&gt;                                                                                                                                 
                                                                                                                                                            
 &lt;/gmd:descriptiveKeywords&gt;                                                                                                                           
                                                                                                                                                            
 &lt;!-- Topic category --&gt;                                                                                                                              
                                                                                                                                                            
 &lt;gmd:topicCategory&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;gmd:MD\_TopicCategoryCode&gt;*http://inspire.ec.europa.eu/metadata-codelist/TopicCategory/geoscientificInformation*&lt;/gmd:MD\_TopicCategoryCode&gt;  
                                                                                                                                                            
 &lt;/gmd:topicCategory&gt;                                                                                                                                 
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;/gmd:MD\_DataIdentification&gt;                                                                                                                        
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;/gmd:identificationInfo&gt;                                                                                                                            
                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;!-- Keywords for services --&gt;                                                                                                                       
                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                   
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;gmd:identificationInfo&gt;                                                                                                                             
                                                                                                                                                            
 &lt;srv:SV\_ServiceIdentification&gt;                                                                                                                      
                                                                                                                                                            
 &lt;!-- free keywords --&gt;                                                                                                                               
                                                                                                                                                            
 &lt;gmd:descriptiveKeywords&gt;                                                                                                                            
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;hydrography&lt;/gco:CharacterString&gt;                                                                                         
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;/gmd:descriptiveKeywords&gt;                                                                                                                           
                                                                                                                                                            
 &lt;!-- Keyword from ISO 19119 codelist of spatial data service categories --&gt;                                                                          
                                                                                                                                                            
 &lt;gmd:descriptiveKeywords&gt;                                                                                                                            
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;humanGeographicViewer&lt;/gco:CharacterString&gt;                                                                               
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:thesaurusName&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;gmd:CI\_Citation&gt;                                                                                                                                   
                                                                                                                                                            
 &lt;gmd:title&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gco:CharacterString&gt;ISO 19119 codelist of spatial data service categories&lt;/gco:CharacterString&gt;                                               
                                                                                                                                                            
 &lt;/gmd:title&gt;                                                                                                                                         
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gmd:CI\_Date&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gco:Date&gt;2007-06-01&lt;/gco:Date&gt;                                                                                                                
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gmd:dateType&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:CI\_DateTypeCode                                                                                                                                   
                                                                                                                                                            
 codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_DateTypeCode*"        
                                                                                                                                                            
 codeListValue="publication"&gt;publication&lt;/gmd:CI\_DateTypeCode&gt;                                                                                    
                                                                                                                                                            
 &lt;/gmd:dateType&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:CI\_Date&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;/gmd:CI\_Citation&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;/gmd:thesaurusName&gt;                                                                                                                                 
                                                                                                                                                            
 &lt;/gmd:descriptiveKeywords&gt;                                                                                                                           
                                                                                                                                                            
 &lt;!-- Keywords from controlled vocabularies --&gt;                                                                                                       
                                                                                                                                                            
 &lt;gmd:descriptiveKeywords&gt;                                                                                                                            
                                                                                                                                                            
 &lt;gmd:keyword&gt;                                                                                                                                        
                                                                                                                                                            
 &lt;gco:CharacterString&gt;Floods&lt;/gco:CharacterString&gt;                                                                                              
                                                                                                                                                            
 &lt;/gmd:keyword&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:thesaurusName&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;gmd:CI\_Citation&gt;                                                                                                                                   
                                                                                                                                                            
 &lt;gmd:title&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gco:CharacterString&gt;GEOSS - Societal Benefit Areas, version 1.0&lt;/gco:CharacterString&gt;                                                         
                                                                                                                                                            
 &lt;/gmd:title&gt;                                                                                                                                         
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gmd:CI\_Date&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:date&gt;                                                                                                                                           
                                                                                                                                                            
 &lt;gco:Date&gt;2010-08-25&lt;/gco:Date&gt;                                                                                                                
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;gmd:dateType&gt;                                                                                                                                       
                                                                                                                                                            
 &lt;gmd:CI\_DateTypeCode                                                                                                                                   
                                                                                                                                                            
 codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_DateTypeCode"          
                                                                                                                                                            
 codeListValue="publication"&gt;publication&lt;/gmd:CI\_DateTypeCode&gt;                                                                                    
                                                                                                                                                            
 &lt;/gmd:dateType&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:CI\_Date&gt;                                                                                                                                      
                                                                                                                                                            
 &lt;/gmd:date&gt;                                                                                                                                          
                                                                                                                                                            
 &lt;/gmd:CI\_Citation&gt;                                                                                                                                  
                                                                                                                                                            
 &lt;/gmd:thesaurusName&gt;                                                                                                                                 
                                                                                                                                                            
 &lt;/gmd:descriptiveKeywords&gt;                                                                                                                           
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;/srv:SV\_ServiceIdentification&gt;                                                                                                                     
                                                                                                                                                            
 ...                                                                                                                                                        
                                                                                                                                                            
 &lt;/gmd:identificationInfo&gt;                                                                                                                            
                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                  |

<span id="_Ref422158340" class="anchor"><span id="_Toc437955433" class="anchor"><span id="_Toc447881053" class="anchor"><span id="_Toc414637489" class="anchor"></span></span></span></span>Spatial data service type - \*not in ISO 19115 core
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

See Section II.3 on resource type.

<span id="_Ref416757089" class="anchor"><span id="_Toc437955434" class="anchor"><span id="_Toc447881054" class="anchor"></span></span></span>Geographic bounding box - \*Geographic location of the dataset (by 4 coordinates or by geographic identifier)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In the core profile of ISO 19115, spatial coverage can be specified either with a bounding box (a geometry) or a geographic identifier. INSPIRE is more restrictive, in that it requires to use a bounding box

Based on that, GeoDCAT-AP models spatial coverage as follows:

-   **Bounding box**: When the area corresponding to the spatial coverage is denoted by a geometry, as in INSPIRE, DCAT-AP recommends the use of the Core Location Vocabulary \[LOCN\], where this is done by using property locn:geometry, having as range a geometry[7] specified as

    -   a URI - e.g., by using the geo URI scheme (IET RFC-5870) \[RFC5870\], or a geohash URI \[GEOHASH, GEOHASH-36\];

    -   a syntax encoding scheme - e.g., geohashes \[GEOHASH, GEOHASH-36\], WKT \[ISO19125-1\], GML \[GML\], KML \[KML\], GeoJSON \[GEOJSON\]; or

    -   a semantic representation - using vocabularies like W3C Lat/long \[LAT-LONG\] or schema.org \[SCHEMA\].

> It is worth noting that currently there is no agreement on a preferred format to be used in RDF for the representation of geometries. In GeoDCAT-AP, geometries can be provided in any, and possibly multiple, encodings, but at least one of the following must be made available: WKT or GML. An additional requirement concerns the coordinate reference system (CRS) used, which may vary on a country or territory basis. The CRS must be specified in the GML or WKT encoding as required by GeoSPARQL \[GEOSPARQL\]. Geometries shall be interpreted using the axis order defined in the spatial reference system used. For example, for CRS84 the axis order is longitude / latitude, whereas for WGS84 the axis order is latitude / longitude. Summarising:

-   Geometries can be provided in multiple encodings, but at least one of the following must be made available: GML and WKT.

-   For GML and WKT, the CRS must be specified as defined in GeoSPARQL \[GEOSPARQL\].

<!-- -->

-   **Geographic identifier**: ISO 19115 core also allows specifying the geographic location using a geographic identifier. Following DCAT-AP, for this, it is recommended to use an HTTP URI from one of the following registers / gazetteers:

    -   The Named Authority Lists operated by the Metadata Registry of the EU Publications office concerning continents \[MDR-CONT\], countries \[MD-COUNTRIES\], and places \[MDR-PLACES\].

    -   If none of the above provides the relevant geographic identifiers, Geonames \[GEONAMES\] should be used.

        If an HTTP URI is not available, the geographical identifier must be expressed with skos:prefLabel, and the reference to the originating controlled vocabulary (if any) must be specified with skos:inScheme. The controlled vocabulary will be described by a name (dct:title) and a last modified data (dct:modified).

As far as geographic identifiers are concerned, following DCAT-AP, GeoDCAT-AP does not prevent the use other vocabularies in addition to the recommended ones. The vocabularies identified by the GeoDCAT-AP WG are listed in Section 6 of the GeoDCAT-AP specification.

The following example shows how to specify the spatial coverage.

| Example                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP using a geographic bounding box. This example uses multiple encodings, namely, the                         
                                                                                                                                                
 \# recommended ones (WKT and GML), plus GeoJSON. To denote the datatype of the GeoJSON literal, the URL of the corresponding                   
                                                                                                                                                
 \# IANA media type.                                                                                                                            
                                                                                                                                                
 \[\] dct:spatial \[ a dct:Location ;                                                                                                           
                                                                                                                                                
 locn:geometry "POLYGON((-10.58 70.09,34.59 70.09,34.59 34.56,-10.58 34.56,                                                                     
                                                                                                                                                
 -10.58 70.09))"^^gsp:wktLiteral ;                                                                                                              
                                                                                                                                                
 locn:geometry "&lt;gml:Envelope srsName=\\"*http://www.opengis.net/def/crs/OGC/1.3/CRS84\\*"&gt;                                               
                                                                                                                                                
 &lt;gml:lowerCorner&gt;34.56 -10.58&lt;/gml:lowerCorner&gt;                                                                                    
                                                                                                                                                
 &lt;gml:upperCorner&gt;70.09 34.59&lt;/gml:upperCorner&gt;                                                                                     
                                                                                                                                                
 &lt;/gml:Envelope&gt;"^^gsp:gmlLiteral \] ;                                                                                                    
                                                                                                                                                
 locn:geometry "{\\"type\\":\\"Polygon\\",\\"crs\\":{\\"type\\":\\"name\\",\\"properties\\":{\\"name\\":\\"urn:ogc:def:crs:OGC:1.3:CRS84\\"}},  
                                                                                                                                                
 \\"coordinates\\":\[\[\[-10.58,70.09\],\[34.59,70.09\],\[34.59,34.56\],\[-10.58,34.56\],\[-10.58,70.09\]\]\]                                   
                                                                                                                                                
 }"^^&lt;*https://www.iana.org/assignments/media-types/application/vnd.geo+json*&gt; \].                                                        
                                                                                                                                                
 \# Resource metadata in GeoDCAT-AP using a geographic identifier                                                                               
                                                                                                                                                
 \#If a URI is used for the geographic identifier (recommended)                                                                                 
                                                                                                                                                
 \[\]                                                                                                                                           
                                                                                                                                                
 dct:spatial &lt;*http://publications.europa.eu/resource/authority/country/NLD*&gt;.                                                            
                                                                                                                                                
 \#If no URI is used for the geographic identifier                                                                                              
                                                                                                                                                
 \[\]                                                                                                                                           
                                                                                                                                                
 dct:spatial \[                                                                                                                                 
                                                                                                                                                
 skos:preflabel "Netherlands"@en;                                                                                                               
                                                                                                                                                
 skos:prefLabel "Nederland"@nl;                                                                                                                 
                                                                                                                                                
 skos:inScheme \[                                                                                                                               
                                                                                                                                                
 dct:title "Countries Authority Table"@en;                                                                                                      
                                                                                                                                                
 dct:modified "2009-01-01"^^xsd:date                                                                                                            
                                                                                                                                                
 \]                                                                                                                                             
                                                                                                                                                
 \].                                                                                                                                            |
| &lt;!-- Resource metadata in ISO19139 using a geographic bounding box --&gt;                                                                  
                                                                                                                                                
 &lt;gmd:MD\_Metadata&gt;                                                                                                                       
                                                                                                                                                
 ...                                                                                                                                            
                                                                                                                                                
 &lt;gmd:identificationInfo&gt;                                                                                                                 
                                                                                                                                                
 &lt;gmd:MD\_DataIdentification&gt;                                                                                                             
                                                                                                                                                
 &lt;gmd:extent&gt;                                                                                                                             
                                                                                                                                                
 &lt;gmd:EX\_Extent&gt;                                                                                                                         
                                                                                                                                                
 &lt;gmd:geographicElement&gt;                                                                                                                  
                                                                                                                                                
 &lt;gmd:EX\_GeographicBoundingBox&gt;                                                                                                          
                                                                                                                                                
 &lt;gmd:extentTypeCode&gt;                                                                                                                     
                                                                                                                                                
 &lt;gco:Boolean&gt;true&lt;/gco:Boolean&gt;                                                                                                    
                                                                                                                                                
 &lt;/gmd:extentTypeCode&gt;                                                                                                                    
                                                                                                                                                
 &lt;gmd:westBoundLongitude&gt;                                                                                                                 
                                                                                                                                                
 &lt;gco:Decimal&gt;-9.227701&lt;/gco:Decimal&gt;                                                                                               
                                                                                                                                                
 &lt;/gmd:westBoundLongitude&gt;                                                                                                                
                                                                                                                                                
 &lt;gmd:eastBoundLongitude&gt;                                                                                                                 
                                                                                                                                                
 &lt;gco:Decimal&gt;2.687637&lt;/gco:Decimal&gt;                                                                                                
                                                                                                                                                
 &lt;/gmd:eastBoundLongitude&gt;                                                                                                                
                                                                                                                                                
 &lt;gmd:southBoundLatitude&gt;                                                                                                                 
                                                                                                                                                
 &lt;gco:Decimal&gt;49.83726&lt;/gco:Decimal&gt;                                                                                                
                                                                                                                                                
 &lt;/gmd:southBoundLatitude&gt;                                                                                                                
                                                                                                                                                
 &lt;gmd:northBoundLatitude&gt;                                                                                                                 
                                                                                                                                                
 &lt;gco:Decimal&gt;60.850441&lt;/gco:Decimal&gt;                                                                                               
                                                                                                                                                
 &lt;/gmd:northBoundLatitude&gt;                                                                                                                
                                                                                                                                                
 &lt;/gmd:EX\_GeographicBoundingBox&gt;                                                                                                         
                                                                                                                                                
 &lt;/gmd:geographicElement&gt;                                                                                                                 
                                                                                                                                                
 &lt;/gmd:EX\_Extent&gt;                                                                                                                        
                                                                                                                                                
 &lt;/gmd:extent&gt;                                                                                                                            
                                                                                                                                                
 &lt;/gmd:MD\_DataIdentification&gt;                                                                                                            
                                                                                                                                                
 &lt;/gmd:identificationInfo&gt;                                                                                                                
                                                                                                                                                
 ...                                                                                                                                            
                                                                                                                                                
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                      |

<span id="_Toc414637490" class="anchor"><span id="_Ref415121232" class="anchor"><span id="_Toc437955435" class="anchor"><span id="_Toc447881055" class="anchor"></span></span></span></span>Temporal reference and metadata date –\*Additional extent information for the dataset (vertical and temporal) and \*Metadata date stamp
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Temporal reference is a composite element consisting of the following possible child elements:

-   temporal extent (temporal coverage);

-   date of publication, last revision, and/or creation.

Based on DCAT-AP, temporal extent is mapped to dct:temporal, having as range dct:PeriodOfTime. The time instant or interval is specified by using properties schema:startDate and schema:endDate, respectively.

By contrast, date of publication, last revision, and creation are mapped, respectively, to dct:issued, dct:modified (both core and extended GeoDCAT-AP profiles), and dct:created (only for the extended profile of GeoDCAT-AP).

DCAT-AP does not foresee a property equivalent to the INSPIRE metadata element metadata date. In INSPIRE, this element is defined as follows ([Part B, §10.2](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e576-14-1)):

The date which specifies when the metadata record was created or updated.

Due to this ambiguity, the proposed mapping for this element is dct:modified.

| Example                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                              
                                                                                                                                                  
 \#\# Creation, publication and last revision dates                                                                                               
                                                                                                                                                  
 \[\] dct:created "2010-03-01"^^xsd:date ;                                                                                                        
                                                                                                                                                  
 dct:issued "2010-10-05"^^xsd:date ;                                                                                                              
                                                                                                                                                  
 dct:modified "2011-09-01"^^xsd:date ;                                                                                                            
                                                                                                                                                  
 \#\# Temporal extent                                                                                                                             
                                                                                                                                                  
 dct:temporal \[ a dct:PeriodOfTime ;                                                                                                             
                                                                                                                                                  
 schema:endDate "2006-12-31"^^xsd:date ;                                                                                                          
                                                                                                                                                  
 schema:startDate "2006-01-01"^^xsd:date \] ;                                                                                                     
                                                                                                                                                  
 foaf:isPrimaryTopicOf                                                                                                                            
                                                                                                                                                  
 \# Metadata on metadata                                                                                                                          
                                                                                                                                                  
 \#\# Metadata date                                                                                                                               
                                                                                                                                                  
 \[ dct:modified "2012-08-13"^^xsd:date \] .                                                                                                      |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                    
                                                                                                                                                  
 &lt;gmd:MD\_Metadata&gt;                                                                                                                         
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;!-- metadata date --&gt;                                                                                                                     
                                                                                                                                                  
 &lt;gmd:dateStamp&gt;                                                                                                                            
                                                                                                                                                  
 &lt;gco:Date&gt;2012-08-13&lt;/gco:Date&gt;                                                                                                      
                                                                                                                                                  
 &lt;/gmd:dateStamp&gt;                                                                                                                           
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;!—temporal extent --&gt;                                                                                                                     
                                                                                                                                                  
 &lt;gmd:extent&gt;                                                                                                                               
                                                                                                                                                  
 &lt;gmd:EX\_Extent&gt;                                                                                                                           
                                                                                                                                                  
 &lt;gmd:temporalElement&gt;                                                                                                                      
                                                                                                                                                  
 &lt;gmd:EX\_TemporalExtent&gt;                                                                                                                   
                                                                                                                                                  
 &lt;gmd:extent&gt;                                                                                                                               
                                                                                                                                                  
 &lt;gml:TimePeriod gml:id="w5633aaa"&gt;                                                                                                         
                                                                                                                                                  
 &lt;gml:beginPosition&gt;2006-01-01&lt;/gml:beginPosition&gt;                                                                                    
                                                                                                                                                  
 &lt;gml:endPosition&gt;2006-12-31&lt;/gml:endPosition&gt;                                                                                        
                                                                                                                                                  
 &lt;/gml:TimePeriod&gt;                                                                                                                          
                                                                                                                                                  
 &lt;/gmd:extent&gt;                                                                                                                              
                                                                                                                                                  
 &lt;/gmd:EX\_TemporalExtent&gt;                                                                                                                  
                                                                                                                                                  
 &lt;/gmd:temporalElement&gt;                                                                                                                     
                                                                                                                                                  
 &lt;/gmd:EX\_Extent&gt;                                                                                                                          
                                                                                                                                                  
 &lt;/gmd:extent&gt;                                                                                                                              
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;!— Publication date (creation and last modification dates encoded similarly) --&gt;                                                          
                                                                                                                                                  
 &lt;gmd:identificationInfo&gt;                                                                                                                   
                                                                                                                                                  
 &lt;gmd:MD\_DataIdentification&gt;                                                                                                               
                                                                                                                                                  
 &lt;gmd:citation&gt;                                                                                                                             
                                                                                                                                                  
 &lt;gmd:CI\_Citation&gt;                                                                                                                         
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;gmd:date&gt;                                                                                                                                 
                                                                                                                                                  
 &lt;gmd:CI\_Date&gt;                                                                                                                             
                                                                                                                                                  
 &lt;gmd:date&gt;                                                                                                                                 
                                                                                                                                                  
 &lt;gco:Date&gt;2010-03-01&lt;/gco:Date&gt;                                                                                                      
                                                                                                                                                  
 &lt;/gmd:date&gt;                                                                                                                                
                                                                                                                                                  
 &lt;gmd:dateType&gt;                                                                                                                             
                                                                                                                                                  
 &lt;gmd:CI\_DateTypeCode codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/*                     
                                                                                                                                                  
 *codelist/ML\_gmxCodelists.xml\#CI\_DateTypeCode*" codeListValue="publication"&gt;publication&lt;/gmd:CI\_DateTypeCode&gt;&lt;/gmd:dateType&gt;  
                                                                                                                                                  
 &lt;/gmd:CI\_Date&gt;                                                                                                                            
                                                                                                                                                  
 &lt;/gmd:date&gt;                                                                                                                                
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;/gmd:CI\_Citation&gt;                                                                                                                        
                                                                                                                                                  
 &lt;/gmd:citation&gt;                                                                                                                            
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;/gmd:MD\_DataIdentification&gt;                                                                                                              
                                                                                                                                                  
 ...                                                                                                                                              
                                                                                                                                                  
 &lt;/gmd:identificationInfo&gt;                                                                                                                  
                                                                                                                                                  
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                        |

<span id="_Toc414637491" class="anchor"><span id="_Ref417894810" class="anchor"><span id="_Toc437955436" class="anchor"><span id="_Ref438647957" class="anchor"><span id="_Toc447881056" class="anchor"></span></span></span></span></span>Lineage - \*Lineage
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Following DCAT-AP, this element is mapped to property dct:provenance.

Since the range of dct:provenance is not a literal, but class dct:ProvenanceStatement, the free-text content of element “lineage” can be expressed by using rdfs:label, as illustrated in the DCMI user guide on publishing metadata \[DCWIKI\].

| Example                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                        
                                                                                                                                                                                                            
 \[\] a dcat:Dataset ;                                                                                                                                                                                      
                                                                                                                                                                                                            
 dct:provenance \[ a dct:ProvenanceStatement ;                                                                                                                                                              
                                                                                                                                                                                                            
 rdfs:label "Forest Map 2006 is derived from the IMAGE2006 (SPOT/LISS scenes) and CORINE2006 landcover dataset. In                                                                                          
                                                                                                                                                                                                            
 addition, MODIS composites are used for the Forest type classification."@en \] .                                                                                                                           |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                              
                                                                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                   
                                                                                                                                                                                                            
 ...                                                                                                                                                                                                        
                                                                                                                                                                                                            
 &lt;gmd:dataQualityInfo&gt;                                                                                                                                                                                
                                                                                                                                                                                                            
 &lt;gmd:DQ\_DataQuality&gt;                                                                                                                                                                                
                                                                                                                                                                                                            
 &lt;gmd:lineage&gt;                                                                                                                                                                                        
                                                                                                                                                                                                            
 &lt;gmd:LI\_Lineage&gt;                                                                                                                                                                                    
                                                                                                                                                                                                            
 &lt;gmd:statement&gt;                                                                                                                                                                                      
                                                                                                                                                                                                            
 &lt;gco:CharacterString&gt; Forest Map 2006 is derived from the IMAGE2006 (SPOT/LISS scenes) and CORINE2006 landcover dataset. In addition, MODIS composites are used for the Forest type classification.  
                                                                                                                                                                                                            
 &lt;/gco:CharacterString&gt;                                                                                                                                                                               
                                                                                                                                                                                                            
 &lt;/gmd:statement&gt;                                                                                                                                                                                     
                                                                                                                                                                                                            
 &lt;/gmd:LI\_Lineage&gt;                                                                                                                                                                                   
                                                                                                                                                                                                            
 &lt;/gmd:lineage&gt;                                                                                                                                                                                       
                                                                                                                                                                                                            
 &lt;/gmd:DQ\_DataQuality&gt;                                                                                                                                                                               
                                                                                                                                                                                                            
 &lt;/gmd:dataQualityInfo&gt;                                                                                                                                                                               
                                                                                                                                                                                                            
 ...                                                                                                                                                                                                        
                                                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                  |

<span id="_Ref419321102" class="anchor"><span id="_Toc437955437" class="anchor"><span id="_Toc447881057" class="anchor"><span id="_Toc414637492" class="anchor"></span></span></span></span>Spatial resolution – Spatial resolution of the dataset
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In DCAT-AP, no equivalent term is foreseen.

There are currently no candidates in existing vocabularies to represent such metadata elements.

Based on this, GeoDCAT-AP defines a provisional mapping, representing spatial resolution in a human-readable form only, using property rdfs:comment.

| Example                                                            |
|--------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                 
                                                                     
 \# Spatial resolution as equivalent scale                           
                                                                     
 \[\] a dcat:Dataset ;                                               
                                                                     
 rdfs:comment "Spatial resolution (equivalent scale): 1:10000"@en .  
                                                                     
 \# Spatial resolution as distance                                   
                                                                     
 \[\] a dcat:Dataset ;                                               
                                                                     
 rdfs:comment "Spatial resolution (distance): 5 km"@en .             |
| &lt;!-- Resource metadata in ISO19139 --&gt;                       
                                                                     
 &lt;gmd:MD\_Resolution&gt;                                          
                                                                     
 &lt;gmd:equivalentScale&gt;                                         
                                                                     
 &lt;gmd:MD\_RepresentativeFraction&gt;                              
                                                                     
 &lt;gmd:denominator&gt;                                             
                                                                     
 &lt;gco:Integer&gt;10000&lt;/gco:Integer&gt;                        
                                                                     
 &lt;/gmd:denominator&gt;                                            
                                                                     
 &lt;/gmd:MD\_RepresentativeFraction&gt;                             
                                                                     
 &lt;/gmd:equivalentScale&gt;                                        
                                                                     
 &lt;/gmd:MD\_Resolution&gt;                                         |

<span id="_Toc414637494" class="anchor"><span id="_Ref416757397" class="anchor"><span id="_Ref416757408" class="anchor"><span id="_Ref417894840" class="anchor"><span id="_Ref417898017" class="anchor"><span id="_Ref417898050" class="anchor"><span id="_Ref419962553" class="anchor"><span id="_Ref420447982" class="anchor"><span id="_Ref420447983" class="anchor"><span id="_Ref422248458" class="anchor"><span id="_Toc437955438" class="anchor"><span id="_Toc447881058" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span>Conformity and data quality - \*not in ISO 19115 core
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The GeoDCAT-AP specification only provides a syntax binding for conformity and not for data quality in general.

In ISO 19115, conformance and quality information is encoded as a quality report containing the result of a test (an evaluation) of a given quality measure, according to an evaluation method, with either a quantitative result (a metric) or a conformance result (pass or fail) as most important outcome.

For encoding conformance, GeoDCAT-AP proposes to use dct:conformsTo and the W3C Provenance Ontology (PROV-O) \[PROV\] as explained in the following paragraphs. For encoding other aspects of data quality, GeoDCAT-AP does not provide a syntax binding as there is a risk that the (future) work of other standards bodies on data quality may make the proposed syntax binding for GeoDCAT-AP outdated. For example, the W3C Data on the Web Best Practices WG is working on a Data Quality Vocabulary (DQV). To limit the impact, it was decided to only provide a partial mapping for Data Quality / Conformance.

DCAT-AP provides a single candidate, dct:conformsTo, which however can be used to map only a conformity of degree ‘conformant’. This is suitable for the core profile of GeoDCAT-AP.

Considering how conformity must be expressed in extended profile of GeoDCAT-AP (see the INSPIRE Metadata Regulation, Part B, [§7](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e415-14-1)), possible candidates are the W3C Evaluation and Report Language (EARL) \[EARL\] and the W3C Provenance Ontology (PROV-O) \[PROV\]. The latter candidate was chosen by the GeoDCAT-AP Working Group, since it would enable wider re-use with respect to the EARL vocabulary, which is more specific, and its use is limited.

PROV-O allows encoding conformity as a test activity (prov:Activity) that generated a result encoded with property ‘prov:generated’, corresponding to the degree of conformity, for which the INSPIRE Registry maintains a URI set, see Section 6 of the GeoDCAT-AP specification. The specification against which the conformance is asserted is encoded via a qualified association (prov:QualifiedAssociation) with a test plan (a prov:Plan) in turn derived from a standard (dct:Standard, also prov:Entity). These associations are made via a chain of properties: ‘prov:qualifiedAssociation’, ‘prov:hadPlan’, and ‘prov:wasDerivedFrom’.

<span id="_Toc437955463" class="anchor"><span id="_Toc447881081" class="anchor"></span></span>Table : Mappings for metadata element ‘conformity’

| Metadata element | *Proposed mapping* |
|------------------|--------------------|
| Conformity       | Specification (M)  |
|                  |                    |
|                  |                    |
|                  |                    |
|                  | Degree (M)         |

In order to grant interoperability with DCAT-AP, when conformity is of degree “conformant”, the proposal is to use both PROV-O and dct:conformsTo for GeoDCAT-AP Extended.

| Example                                                                                                                                                                                                                                            |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *\# Resource metadata in GeoDCAT-AP*                                                                                                                                                                                                               
                                                                                                                                                                                                                                                     
 prov:wasUsedBy \[                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 a prov:Activity;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                     
 *\# Conformity degree*                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                     
 prov:generated \[                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 dct:type &lt;http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity/conformant&gt; ;                                                                                                                                                      
                                                                                                                                                                                                                                                     
 dct:description “See the referenced specification”@en                                                                                                                                                                                               
                                                                                                                                                                                                                                                     
 prov:qualifiedAssociation \[                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                     
 prov:hadPlan \[                                                                                                                                                                                                                                     
                                                                                                                                                                                                                                                     
 a prov:Plan;                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                     
 prov:wasDerivedFrom \[                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                     
 *\# Specification*                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                     
 a prov:Entity, dct:Standard;                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                     
 dct:title "COMMISSION REGULATION (EC) No 976/2009 of 19 October 2009 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards the Network Services"@en                                                             
                                                                                                                                                                                                                                                     
 dct:issued "2009-10-20"^^xsd:date                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 \]                                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                     
 \];                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                     
 \];                                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                     
 \] .                                                                                                                                                                                                                                                |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                                                                       
                                                                                                                                                                                                                                                     
 &lt;gmd:result&gt;                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                     
 &lt;gmd:DQ\_ConformanceResult&gt;                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 &lt;gmd:specification&gt;                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                     
 &lt;gmd:CI\_Citation&gt;                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                     
 &lt;gmd:title&gt;                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 &lt;gco:CharacterString&gt;COMMISSION REGULATION (EC) No 976/2009 of 19 October 2009 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards the Network Services&lt;/gco:CharacterString&gt;                     
                                                                                                                                                                                                                                                     
 &lt;/gmd:title&gt;                                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                     
 &lt;gmd:date&gt;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                     
 &lt;gmd:CI\_Date&gt;                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                     
 &lt;gmd:date&gt;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                     
 &lt;gco:Date&gt;2009-10-20&lt;/gco:Date&gt;                                                                                                                                                                                                         
                                                                                                                                                                                                                                                     
 &lt;/gmd:date&gt;                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 &lt;gmd:dateType&gt;                                                                                                                                                                                                                                
                                                                                                                                                                                                                                                     
 &lt;gmd:CI\_DateTypeCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_DateTypeCode" codeListValue="publication"&gt;publication&lt;/gmd:CI\_DateTypeCode&gt;  
                                                                                                                                                                                                                                                     
 &lt;/gmd:dateType&gt;                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                     
 &lt;/gmd:CI\_Date&gt;                                                                                                                                                                                                                               
                                                                                                                                                                                                                                                     
 &lt;/gmd:date&gt;                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                     
 &lt;/gmd:CI\_Citation&gt;                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                     
 &lt;/gmd:specification&gt;                                                                                                                                                                                                                          
                                                                                                                                                                                                                                                     
 &lt;gmd:explanation&gt;                                                                                                                                                                                                                             
                                                                                                                                                                                                                                                     
 &lt;gco:CharacterString&gt; &lt;/gco:CharacterString&gt;                                                                                                                                                                                            
                                                                                                                                                                                                                                                     
 &lt;/gmd:explanation&gt;                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                     
 &lt;gmd:pass&gt;&lt;gco:Boolean&gt;true&lt;/gco:Boolean&gt;&lt;/gmd:pass&gt;                                                                                                                                                                        
                                                                                                                                                                                                                                                     
 &lt;/gmd:DQ\_ConformanceResult&gt;                                                                                                                                                                                                                  
                                                                                                                                                                                                                                                     
 &lt;/gmd:result&gt;                                                                                                                                                                                                                                 |

The PROV-O-based approach might be revised in the future – but still supported for backward interoperability –, if future standard vocabularies will be able to address GeoDCAT-AP requirement.

<span id="_Ref416757423" class="anchor"><span id="_Toc437955439" class="anchor"><span id="_Ref438647990" class="anchor"><span id="_Ref438648009" class="anchor"><span id="_Toc447881059" class="anchor"></span></span></span></span></span>Conditions for access and use and limitations on public access – Use limitation and access / other constraints
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In DCAT-AP, licensing information is specified on (a) data catalogues (services) and on (b) the distribution(s) of a dataset, and not on the dataset itself. The principle is that different dataset distributions may be associated with different licensing terms. Moreover, DCAT-AP recommends the use of dct:accessRights for specifying access conditions.

Based on this, GeoDCAT-AP models use and access limitations by using, respectively, dct:license and dct:accessRights.

Since the range of these properties is not a literal, but, respectively, classes dct:LicenseDocument and dct:RightsStatement, the free-text content of the corresponding ISO 19115 / INSPIRE metadata elements can be expressed by using rdfs:label, as illustrated in \[DCWIKI\].

NB: It is a recommended good practice to mint URIs for licence documents and right statements.

| Example                                                                                                                                                                                                                   |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                        
                                                                                                                                                                                                                            
 \[\] dcat:distribution \[ a dcat:Distribution ;                                                                                                                                                                            
                                                                                                                                                                                                                            
 dct:license \[ a dct:LicenseDocument ;                                                                                                                                                                                     
                                                                                                                                                                                                                            
 rdfs:label "Reuse is authorised according to the European Commission legal notice at                                                                                                                                       
                                                                                                                                                                                                                            
 *http://ec.europa.eu/geninfo/legal\_notices\_en.htm*"@en \] ;                                                                                                                                                              
                                                                                                                                                                                                                            
 dct:accessRights \[ a dct:RightsStatement ;                                                                                                                                                                                
                                                                                                                                                                                                                            
 rdfs:label "no limitation"@en \] \] .                                                                                                                                                                                      
                                                                                                                                                                                                                            
 \# Resource metadata in GeoDCAT-AP (using URI for the licence)                                                                                                                                                             
                                                                                                                                                                                                                            
 \[\] dcat:distribution \[ a dcat:Distribution ;                                                                                                                                                                            
                                                                                                                                                                                                                            
 dct:license &lt;*http://ec.europa.eu/geninfo/legal\_notices\_en.htm*&gt; ;                                                                                                                                                 
                                                                                                                                                                                                                            
 dct:accessRights \[ a dct:RightsStatement ;                                                                                                                                                                                
                                                                                                                                                                                                                            
 rdfs:label "no limitation"@en \] \] .                                                                                                                                                                                      |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                                              
                                                                                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                                   
                                                                                                                                                                                                                            
 ...                                                                                                                                                                                                                        
                                                                                                                                                                                                                            
 &lt;gmd:MD\_LegalConstraints&gt;                                                                                                                                                                                           
                                                                                                                                                                                                                            
 &lt;gmd:useLimitation&gt;                                                                                                                                                                                                  
                                                                                                                                                                                                                            
 &lt;gco:CharacterString&gt;Reuse is authorised according to the European Commission legal notice at                                                                                                                        
                                                                                                                                                                                                                            
 *http://ec.europa.eu/geninfo/legal\_notices\_en.htm.*&lt;/gco:CharacterString&gt;                                                                                                                                          
                                                                                                                                                                                                                            
 &lt;/gmd:useLimitation&gt;                                                                                                                                                                                                 
                                                                                                                                                                                                                            
 &lt;gmd:accessConstraints&gt;                                                                                                                                                                                              
                                                                                                                                                                                                                            
 &lt;gmd:MD\_RestrictionCode codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#MD\_RestrictionCode*" codeListValue="otherRestrictions"/&gt;  
                                                                                                                                                                                                                            
 &lt;/gmd:accessConstraints&gt;                                                                                                                                                                                             
                                                                                                                                                                                                                            
 &lt;gmd:otherConstraints&gt;                                                                                                                                                                                               
                                                                                                                                                                                                                            
 &lt;gco:CharacterString&gt;No limitation&lt;/gco:CharacterString&gt;                                                                                                                                                       
                                                                                                                                                                                                                            
 &lt;/gmd:otherConstraints&gt;                                                                                                                                                                                              
                                                                                                                                                                                                                            
 &lt;/gmd:MD\_LegalConstraints&gt;                                                                                                                                                                                          
                                                                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                  
                                                                                                                                                                                                                            
 &lt;!-- Resource metadata in ISO19139: using a licence URI --&gt;                                                                                                                                                          
                                                                                                                                                                                                                            
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                                   
                                                                                                                                                                                                                            
 ...                                                                                                                                                                                                                        
                                                                                                                                                                                                                            
 &lt;gmd:MD\_LegalConstraints&gt;                                                                                                                                                                                           
                                                                                                                                                                                                                            
 &lt;gmd:useLimitation&gt;                                                                                                                                                                                                  
                                                                                                                                                                                                                            
 &lt;gmx:Anchor xlink:href=" *http://ec.europa.eu/geninfo/legal\_notices\_en.htm*"&lt;/gmx:Anchor &gt;                                                                                                                      
                                                                                                                                                                                                                            
 &lt;/gmd:useLimitation&gt;                                                                                                                                                                                                 
                                                                                                                                                                                                                            
 &lt;gmd:accessConstraints&gt;                                                                                                                                                                                              
                                                                                                                                                                                                                            
 &lt;gmd:MD\_RestrictionCode codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#MD\_RestrictionCode*" codeListValue="otherRestrictions"/&gt;  
                                                                                                                                                                                                                            
 &lt;/gmd:accessConstraints&gt;                                                                                                                                                                                             
                                                                                                                                                                                                                            
 &lt;gmd:otherConstraints&gt;                                                                                                                                                                                               
                                                                                                                                                                                                                            
 &lt;gco:CharacterString&gt;No limitation&lt;/gco:CharacterString&gt;                                                                                                                                                       
                                                                                                                                                                                                                            
 &lt;/gmd:otherConstraints&gt;                                                                                                                                                                                              
                                                                                                                                                                                                                            
 &lt;/gmd:MD\_LegalConstraints&gt;                                                                                                                                                                                          
                                                                                                                                                                                                                            
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                  |

<span id="_Toc414637493" class="anchor"><span id="_Ref415121303" class="anchor"><span id="_Ref416757447" class="anchor"><span id="_Ref417900130" class="anchor"><span id="_Ref417900221" class="anchor"><span id="_Toc437955440" class="anchor"><span id="_Ref438648020" class="anchor"><span id="_Ref438648439" class="anchor"><span id="_Ref438648450" class="anchor"><span id="_Ref438648471" class="anchor"><span id="_Ref438648487" class="anchor"><span id="_Toc447881060" class="anchor"></span></span></span></span></span></span></span></span></span></span></span></span>Responsible party and metadata point of contact - \*Dataset responsible party and \*Metadata point of contact
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

DCAT-AP supports properties to denote the publisher and the contact point for a dataset.

By contrast, ISO 19115 and the INSPIRE Metadata Regulation foresee 11 possible relationships between a resource (a dataset, a dataset series, a service) and an agent (organisation), plus one for metadata. For some of them, suitable candidates exist from widely used vocabularies (in particular, DCMI Metadata Terms \[DCTERMS\]). However, for some of them no suitable candidate is available in the existing vocabularies (in particular, for roles “user” and “processor”).

In the extended profile of GeoDCAT-AP, the W3C PROV ontology \[PROV\] is used to specify the relationship between the resource and the responsible organisation. The W3C vCard ontology \[VCARD\] will then be used to specify the contact information concerning the responsible party. Finally, the responsible party role will be specified by using dct:type, and using the relevant code list values from the INSPIRE Registry – reference register:

<http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole>

These mappings are illustrated in the following table.

<span id="_Toc437955464" class="anchor"><span id="_Toc447881082" class="anchor"></span></span>Table : Mappings for metadata element ‘responsible party’

| Metadata element  | Proposed mapping       |
|-------------------|------------------------|
| Responsible party | Responsible party      |
|                   |                        |
|                   | Responsible party role |

This option has the advantage of preserving the semantics in the original metadata, and of preventing information loss. However, it does not rely on RDF properties used in DCAT-AP.

For these reasons, the GeoDCAT-AP overall approach is as follows:

-   If suitable candidates exist from widely used vocabularies, use them to represent the corresponding responsible parties and their roles, based on an agreed definition of 1-to-1 mappings. Otherwise:

-   Represent responsible organisations by using the PROV ontology.

As mentioned earlier, the latter option is supported only in the extended profile of GeoDCAT-AP.

The following table lists the GeoDCAT-AP mappings for responsible party roles, taking into account only widely used vocabularies.

<span id="_Toc437955465" class="anchor"><span id="_Toc447881083" class="anchor"></span></span>Table : Responsible party roles

| ISO 19115:2003         | INSPIRE Metadata Regulation                                                     | Description                                                                                                                     | Proposed RDF mapping                                        
                                                                                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                              (where not available prov:qualifiedAttribution can be used)  |
|------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------|
| Resource provider      | [**Part B §6.1**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2082-14-1)  | Party that supplies the resource.                                                                                               | N/A                                                         |
| Custodian              | [**Part B §6.2**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2092-14-1)  | Party that accepts accountability and responsibility for the data and ensures appropriate care and maintenance of the resource. | N/A                                                         |
| Owner                  | [**Part B §6.3**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2102-14-1)  | Party that owns the resource.                                                                                                   | dct:rightsHolder                                            |
| User                   | [**Part B §6.4**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2112-14-1)  | Party who uses the resource.                                                                                                    | N/A                                                         |
| Distributor            | [**Part B §6.5**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2122-14-1)  | Party who distributes the resource                                                                                              | N/A                                                         |
| Originator             | [**Part B §6.6**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2132-14-1)  | Party who created the resource.                                                                                                 | N/A                                                         |
| Point of contact       | [**Part B §6.7**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2142-14-1)  | Party who can be contacted for acquiring knowledge about or acquisition of the resource.                                        | dcat:contactPoint                                           |
| Principal investigator | [**Part B §6.8**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2152-14-1)  | Key party responsible for gathering information and conducting research                                                         | N/A                                                         |
| Processor              | [**Part B §6.9**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2162-14-1)  | Party who has processed the data in a manner such that the resource has been modified.                                          | N/A                                                         |
| Publisher              | [**Part B §6.10**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2172-14-1) | Party who published the resource                                                                                                | dct:publisher                                               |
| Author                 | [**Part B §6.11**](http://eur-lex.europa.eu/eli/reg/com/2008/1205#d1e2183-14-1) | Party who authored the resource.                                                                                                | dct:creator                                                 |

In the following example, the same organisation is both the data custodian and the metadata point of contact.

| Example                                                                                                                                                                                                  |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                       
                                                                                                                                                                                                           
 \[\] dcat:contactPoint \[ a vcard:Organization ;                                                                                                                                                          
                                                                                                                                                                                                           
 foaf:mbox &lt;mailto:bag@kadaster.nl&gt; ;                                                                                                                                                                
                                                                                                                                                                                                           
 foaf:name "Kadaster"@nl \] ;                                                                                                                                                                              
                                                                                                                                                                                                           
 prov:qualifiedAttribution                                                                                                                                                                                 
                                                                                                                                                                                                           
 \[ a prov:Attribution ;                                                                                                                                                                                   
                                                                                                                                                                                                           
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole/custodian*&gt; ;                                                                                                         
                                                                                                                                                                                                           
 prov:agent \[ a vcard:Kind ;                                                                                                                                                                              
                                                                                                                                                                                                           
 vcard:hasEmail &lt;mailto:bag@kadaster.nl&gt; ;                                                                                                                                                           
                                                                                                                                                                                                           
 vcard:organization-name "Kadaster"@nl \] \] ;                                                                                                                                                             
                                                                                                                                                                                                           
 foaf:isPrimaryTopicOf                                                                                                                                                                                     
                                                                                                                                                                                                           
 \# Metadata on metadata in GeoDCAT-AP                                                                                                                                                                     
                                                                                                                                                                                                           
 \[ dcat:contactPoint \[ a vcard:Kind ;                                                                                                                                                                    
                                                                                                                                                                                                           
 vcard:hasEmail &lt;mailto:bag@kadaster.nl&gt; ;                                                                                                                                                           
                                                                                                                                                                                                           
 vcard:organization-name "Kadaster"@nl \] ;                                                                                                                                                                
                                                                                                                                                                                                           
 prov:qualifiedAttribution \[ a prov:Attribution ;                                                                                                                                                         
                                                                                                                                                                                                           
 dct:type &lt;*http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole/pointOfContact*&gt; ;                                                                                                    
                                                                                                                                                                                                           
 prov:agent \[ a vcard:Kind ;                                                                                                                                                                              
                                                                                                                                                                                                           
 vcard:hasEmail &lt;mailto:bag@kadaster.nl&gt; ;                                                                                                                                                           
                                                                                                                                                                                                           
 vcard:hasURL &lt;http://www.kadaster.nl/bag&gt; ;                                                                                                                                                         
                                                                                                                                                                                                           
 vcard:organization-name "Kadaster"@nl \] \] \] .                                                                                                                                                          |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                             
                                                                                                                                                                                                           
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 ...                                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;gmd:pointOfContact&gt;                                                                                                                                                                                
                                                                                                                                                                                                           
 &lt;gmd:CI\_ResponsibleParty&gt;                                                                                                                                                                          
                                                                                                                                                                                                           
 &lt;gmd:organisationName&gt;                                                                                                                                                                              
                                                                                                                                                                                                           
 &lt;gco:CharacterString&gt;Kadaster&lt;/gco:CharacterString&gt;                                                                                                                                           
                                                                                                                                                                                                           
 &lt;/gmd:organisationName&gt;                                                                                                                                                                             
                                                                                                                                                                                                           
 &lt;gmd:contactInfo&gt;                                                                                                                                                                                   
                                                                                                                                                                                                           
 &lt;gmd:CI\_Contact&gt;                                                                                                                                                                                   
                                                                                                                                                                                                           
 &lt;gmd:address&gt;                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;gmd:CI\_Address&gt;                                                                                                                                                                                   
                                                                                                                                                                                                           
 &lt;gmd:electronicMailAddress&gt;                                                                                                                                                                         
                                                                                                                                                                                                           
 &lt;gco:CharacterString&gt;bag@kadaster.nl&lt;/gco:CharacterString&gt;                                                                                                                                    
                                                                                                                                                                                                           
 &lt;/gmd:electronicMailAddress&gt;                                                                                                                                                                        
                                                                                                                                                                                                           
 &lt;/gmd:CI\_Address&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 &lt;/gmd:address&gt;                                                                                                                                                                                      
                                                                                                                                                                                                           
 &lt;gmd:onlineResource&gt;                                                                                                                                                                                
                                                                                                                                                                                                           
 &lt;gmd:CI\_OnlineResource&gt;                                                                                                                                                                            
                                                                                                                                                                                                           
 &lt;gmd:linkage&gt;                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;gmd:URL&gt;*http://www.kadaster.nl/bag*&lt;/gmd:URL&gt;                                                                                                                                               
                                                                                                                                                                                                           
 &lt;/gmd:linkage&gt;                                                                                                                                                                                      
                                                                                                                                                                                                           
 &lt;/gmd:CI\_OnlineResource&gt;                                                                                                                                                                           
                                                                                                                                                                                                           
 &lt;/gmd:onlineResource&gt;                                                                                                                                                                               
                                                                                                                                                                                                           
 &lt;/gmd:CI\_Contact&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 &lt;/gmd:contactInfo&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 &lt;gmd:role&gt;                                                                                                                                                                                          
                                                                                                                                                                                                           
 &lt;gmd:CI\_RoleCode codeListValue="custodian" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_RoleCode*"/&gt;       
                                                                                                                                                                                                           
 &lt;/gmd:role&gt;                                                                                                                                                                                         
                                                                                                                                                                                                           
 &lt;/gmd:CI\_ResponsibleParty&gt;                                                                                                                                                                         
                                                                                                                                                                                                           
 &lt;/gmd:pointOfContact&gt;                                                                                                                                                                               
                                                                                                                                                                                                           
 ...                                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                 
                                                                                                                                                                                                           
 &lt;!-- Metadata on metadata in ISO19139 --&gt;                                                                                                                                                           
                                                                                                                                                                                                           
 &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 ...                                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;gmd:contact&gt;                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;gmd:CI\_ResponsibleParty&gt;                                                                                                                                                                          
                                                                                                                                                                                                           
 &lt;gmd:organisationName&gt;                                                                                                                                                                              
                                                                                                                                                                                                           
 &lt;gco:CharacterString&gt;Kadaster&lt;/gco:CharacterString&gt;                                                                                                                                           
                                                                                                                                                                                                           
 &lt;/gmd:organisationName&gt;                                                                                                                                                                             
                                                                                                                                                                                                           
 &lt;gmd:contactInfo&gt;                                                                                                                                                                                   
                                                                                                                                                                                                           
 ...                                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;/gmd:contactInfo&gt;                                                                                                                                                                                  
                                                                                                                                                                                                           
 &lt;gmd:role&gt;                                                                                                                                                                                          
                                                                                                                                                                                                           
 &lt;gmd:CI\_RoleCode codeListValue="pointofContact" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#CI\_RoleCode*"/&gt;  
                                                                                                                                                                                                           
 &lt;/gmd:role&gt;                                                                                                                                                                                         
                                                                                                                                                                                                           
 &lt;/gmd:CI\_ResponsibleParty&gt;                                                                                                                                                                         
                                                                                                                                                                                                           
 &lt;/gmd:contact&gt;                                                                                                                                                                                      
                                                                                                                                                                                                           
 ...                                                                                                                                                                                                       
                                                                                                                                                                                                           
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                 |

<span id="_Ref417900012" class="anchor"><span id="_Toc437955441" class="anchor"><span id="_Toc447881061" class="anchor"><span id="_Toc414637495" class="anchor"></span></span></span></span>\*Metadata file identifier
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This element identifies a metadata record.

Metadata file identifiers are mapped to dct:identifier.

| Example                                                                |
|------------------------------------------------------------------------|
| \# Metadata on metadata in GeoDCAT-AP                                  
                                                                         
 \[\] a dcat:CatalogRecord ;                                             
                                                                         
 dct:identifier "947e5a55-e548-11e1-9105-0017085a97ab"^^xsd:string \] .  |
| &lt;!-- Resource metadata in ISO19139 --&gt;                           
                                                                         
 &lt;gmd:MD\_Metadata&gt;                                                
                                                                         
 &lt;!-- Metadata on metadata --&gt;                                     
                                                                         
 ...                                                                     
                                                                         
 &lt;gmd:fileIdentifier&gt;                                              
                                                                         
 &lt;gco:CharacterString&gt;                                             
                                                                         
 947e5a55-e548-11e1-9105-0017085a97ab                                    
                                                                         
 &lt;/gco:CharacterString&gt;                                            
                                                                         
 &lt;/gmd:fileIdentifier&gt;                                             
                                                                         
 ...                                                                     
                                                                         
 &lt;/gmd:MD\_Metadata&gt;                                               |

If the metadata file identifier is or can be encoded as an HTTP URI, it can also be used as the URI of the catalogue record (see the following example).

| Example                                                                                          |
|--------------------------------------------------------------------------------------------------|
| \# Metadata on metadata in GeoDCAT-AP                                                            
                                                                                                   
 &lt;http://some.site/some/path/947e5a55-e548-11e1-9105-0017085a97ab&gt;                           
                                                                                                   
 a dcat:CatalogRecord ;                                                                            
                                                                                                   
 dct:identifier "http://some.site/some/path/947e5a55-e548-11e1-9105-0017085a97ab"^^xsd:anyURI \].  |

<span id="_Ref417900062" class="anchor"><span id="_Toc437955442" class="anchor"><span id="_Toc447881062" class="anchor"></span></span></span>\*Metadata standard name, \*Metadata standard version
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Following DCAT-AP, GeoDCAT-AP uses dct:conformsTo to encode information about the metadata standard name and metadata standard version.

The metadata on metadata is encoded as a dcat:CatalogRecord.

<span id="_Toc437955466" class="anchor"><span id="_Toc447881084" class="anchor"></span></span>Table : Metadata standard name and metadata standard version

| Metadata element  | *Proposed mapping*        |
|-------------------|---------------------------|
| Metadata standard | Metadata standard name    |
|                   | Metadata standard version |

The following example shows a GeoDCAT-AP metadata record obtained from one conformant with ISO 19115.

| Example                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------|
| \# Metadata on metadata in GeoDCAT-AP                                                                              
                                                                                                                     
 \[\] a dcat:CatalogRecord ;                                                                                         
                                                                                                                     
 dct:conformsTo \[                                                                                                   
                                                                                                                     
 \# Standard name and version of the GeoDCAT-AP record                                                               
                                                                                                                     
 dct:title "GeoDCAT-AP Extended profile"@en ;                                                                        
                                                                                                                     
 owl:versionInfo "1.0".                                                                                              
                                                                                                                     
 \] .                                                                                                                |
| &lt;!-- Resource metadata in ISO19139 for datasets --&gt;                                                          
                                                                                                                     
 &lt;gmd:MD\_Metadata&gt;                                                                                            
                                                                                                                     
 ...                                                                                                                 
                                                                                                                     
 &lt;gmd:metadataStandardName&gt;                                                                                    
                                                                                                                     
 &lt;gco:CharacterString&gt;ISO 19115&lt;/gco:CharacterString&gt;                                                    
                                                                                                                     
 &lt;/gmd:metadataStandardName&gt;                                                                                   
                                                                                                                     
 &lt;gmd:metadataStandardVersion&gt;                                                                                 
                                                                                                                     
 &lt;gco:CharacterString&gt;Nederlands metadata profiel op ISO 19115 voor geografie 1.3&lt;/gco:CharacterString&gt;  
                                                                                                                     
 &lt;/gmd:metadataStandardVersion&gt;                                                                                
                                                                                                                     
 &lt;/gmd:MD\_Metadata&gt;                                                                                           |

To represent the standard name and version of the source ISO record, the GeoDCAT-AP metadata record must be extended as in the following example.

| Example                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------|
| \# Metadata on metadata in GeoDCAT-AP                                                                              
                                                                                                                     
 \[\] a dcat:CatalogRecord ;                                                                                         
                                                                                                                     
 dct:conformsTo \[                                                                                                   
                                                                                                                     
 \# Standard name and version of the GeoDCAT-AP record                                                               
                                                                                                                     
 dct:title "GeoDCAT-AP Extended profile"@en ;                                                                        
                                                                                                                     
 owl:versionInfo "1.0".                                                                                              
                                                                                                                     
 \] ;                                                                                                                
                                                                                                                     
 dct:source \[                                                                                                       
                                                                                                                     
 \# Standard name and version of the source ISO 19115 record                                                         
                                                                                                                     
 a dcat:CatalogRecord ;                                                                                              
                                                                                                                     
 dct:conformsTo \[                                                                                                   
                                                                                                                     
 dct:title "ISO 19115"@en ;                                                                                          
                                                                                                                     
 owl:versionInfo "Nederlands metadata profiel op ISO 19115 voor geografie 1.3".                                      
                                                                                                                     
 \] .                                                                                                                |
| &lt;!-- Resource metadata in ISO19139 for datasets --&gt;                                                          
                                                                                                                     
 &lt;gmd:MD\_Metadata&gt;                                                                                            
                                                                                                                     
 ...                                                                                                                 
                                                                                                                     
 &lt;gmd:metadataStandardName&gt;                                                                                    
                                                                                                                     
 &lt;gco:CharacterString&gt;ISO 19115&lt;/gco:CharacterString&gt;                                                    
                                                                                                                     
 &lt;/gmd:metadataStandardName&gt;                                                                                   
                                                                                                                     
 &lt;gmd:metadataStandardVersion&gt;                                                                                 
                                                                                                                     
 &lt;gco:CharacterString&gt;Nederlands metadata profiel op ISO 19115 voor geografie 1.3&lt;/gco:CharacterString&gt;  
                                                                                                                     
 &lt;/gmd:metadataStandardVersion&gt;                                                                                
                                                                                                                     
 &lt;/gmd:MD\_Metadata&gt;                                                                                           |

<span id="_Toc437955443" class="anchor"><span id="_Toc447881063" class="anchor"></span></span>\*Metadata characterset
---------------------------------------------------------------------------------------------------------------------

See Section II.24.

<span id="_Toc437955444" class="anchor"><span id="_Toc447881064" class="anchor"></span></span>Metadata point of contact - \*Metadata point of contact
-----------------------------------------------------------------------------------------------------------------------------------------------------

See Section II.16.

<span id="_Ref420654001" class="anchor"><span id="_Toc437955445" class="anchor"><span id="_Toc447881065" class="anchor"></span></span></span>Metadata date - \*Metadata date stamp
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

See Section II.11.

<span id="_Toc437955446" class="anchor"><span id="_Toc447881066" class="anchor"><span id="_Toc414637496" class="anchor"></span></span></span>Metadata language - \*Metadata language
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

See Section II.7.

<span id="_Toc414637498" class="anchor"><span id="_Ref420056318" class="anchor"><span id="_Toc437955447" class="anchor"><span id="_Toc447881067" class="anchor"></span></span></span></span>Coordinate reference systems and Temporal reference systems – \*Reference System
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In DCAT-AP, no equivalent term is foreseen. This is also the case for the NeoGeo \[NEOGEO\], GeoSPARQL \[GEOSPARQL\], and the Core Location Vocabulary \[LOCN\].

Based on this, these elements are provisionally mapped to property dct:conformsTo. Moreover, in order to indicate that the object of dct:conformsTo denotes a reference system, an additional statement with predicate dct:type is added, with a code list value defining the notion of (spatial / temporal) reference system, taken from the glossary operated by the INSPIRE Registry.

More precisely, the following URIs should be used to denote, respectively, spatial and temporal reference systems:

-   <http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem>

-   <http://inspire.ec.europa.eu/glossary/TemporalReferenceSystem>

The reference system identifier should be preferably represented with an HTTP URI. In particular, spatial reference systems should be specified by using the corresponding URIs from the “EPSG coordinate reference systems” register operated by the Open Geospatial Consortium.

In this register, the URI prefix for coordinate reference systems is the following one:

<http://www.opengis.net/def/crs/EPSG/0/>

followed by the number identifying the coordinate reference system in the EPSG register. For instance, the following URI

<http://www.opengis.net/def/crs/EPSG/0/4258>

identifies coordinate reference system EPSG 4258, corresponding to ETRS89 (European Terrestrial Referent System 1989).

| Example                                                                          |
|----------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                               
                                                                                   
 \[\] a dcat:Dataset ;                                                             
                                                                                   
 dct:conformsTo *&lt;*<http://www.opengis.net/def/crs/EPSG/0/4258>*&gt;* .         
                                                                                   
 *&lt;*<http://www.opengis.net/def/crs/EPSG/0/4258>*&gt; *                         
                                                                                   
 dct:type &lt;<http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem>&gt; .  |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                     
                                                                                   
 &lt;gmd:referenceSystemInfo&gt;                                                   
                                                                                   
 &lt;gmd:MD\_ReferenceSystem&gt;                                                   
                                                                                   
 &lt;gmd:referenceSystemIdentifier&gt;                                             
                                                                                   
 &lt;gmd:RS\_Identifier&gt;                                                        
                                                                                   
 &lt;gmd:code&gt;                                                                  
                                                                                   
 &lt;gco:CharacterString&gt;                                                       
                                                                                   
 http://www.opengis.net/def/crs/EPSG/0/4258                                        
                                                                                   
 &lt;/gco:CharacterString&gt;                                                      
                                                                                   
 &lt;/gmd:code&gt;                                                                 
                                                                                   
 ...                                                                               
                                                                                   
 &lt;/gmd:RS\_Identifier&gt;                                                       
                                                                                   
 &lt;/gmd:referenceSystemIdentifier&gt;                                            
                                                                                   
 &lt;/gmd:MD\_ReferenceSystem&gt;                                                  
                                                                                   
 &lt;/gmd:referenceSystemInfo&gt;                                                  |

If not represented with an HTTP URI, the reference system identifier must be mapped to dct:identifier, as in the following example.

| Example                                                                        |
|--------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                             
                                                                                 
 \[\] a dcat:Dataset ;                                                           
                                                                                 
 dct:conformsTo \[                                                               
                                                                                 
 dct:identifer "EPSG:4258"^^xsd:string ;                                         
                                                                                 
 dct:type *&lt;http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem&gt;*  
                                                                                 
 \] .                                                                            |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                   
                                                                                 
 &lt;gmd:referenceSystemInfo&gt;                                                 
                                                                                 
 &lt;gmd:MD\_ReferenceSystem&gt;                                                 
                                                                                 
 &lt;gmd:referenceSystemIdentifier&gt;                                           
                                                                                 
 &lt;gmd:RS\_Identifier&gt;                                                      
                                                                                 
 &lt;gmd:code&gt;                                                                
                                                                                 
 &lt;gco:CharacterString&gt;EPSG:4258&lt;/gco:CharacterString&gt;                
                                                                                 
 &lt;/gmd:code&gt;                                                               
                                                                                 
 ...                                                                             
                                                                                 
 &lt;/gmd:RS\_Identifier&gt;                                                     
                                                                                 
 &lt;/gmd:referenceSystemIdentifier&gt;                                          
                                                                                 
 &lt;/gmd:MD\_ReferenceSystem&gt;                                                
                                                                                 
 &lt;/gmd:referenceSystemInfo&gt;                                                |

<span id="_Ref417900488" class="anchor"><span id="_Ref417900605" class="anchor"><span id="_Toc437955448" class="anchor"><span id="_Toc447881068" class="anchor"></span></span></span></span>Character encoding - \*Dataset character set and \*Metadata character set
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In DCAT and DCAT-AP, the specification of the character encoding of a dataset and the character encoding of a metadata record is not explicitly foreseen.

According to RFC 4288 \[RFC4288\], the character set can be part of the media type specification, but only for type “text”. By contrast, in INSPIRE the character set can be specified also for other media types.

The W3C Content vocabulary \[CNT\] provides a possibly suitable candidate, namely, property cnt:characterEncoding, taking as value the character set names in the IANA register \[IANA-CS\]. GeoDCAT-AP uses this property.

Character encoding in ISO 19115 metadata is specified with a code list that can be mapped to the corresponding codes in the IANA Character Sets register[8], as shown in the following table (entries with 1-to-many mappings are in italic).

| ISO 19115 - MD\_CharacterSetCode | Description                                                                                                                       | IANA            |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|-----------------|
| ucs2                             | 16-bit fixed size Universal Character Set, based on ISO/IEC 10646                                                                 | ISO-10646-UCS-2 |
| ucs4                             | 32-bit fixed size Universal Character Set, based on ISO/IEC 10646                                                                 | ISO-10646-UCS-4 |
| utf7                             | 7-bit variable size UCS Transfer Format, based on ISO/IEC 10646                                                                   | UTF-7           |
| utf8                             | 8-bit variable size UCS Transfer Format, based on ISO/IEC 10646                                                                   | UTF-8           |
| utf16                            | 16-bit variable size UCS Transfer Format, based on ISO/IEC 10646                                                                  | UTF-16          |
| 8859part1                        | ISO/IEC 8859-1, Information technology - 8-bit single byte coded graphic character sets - Part 1 : Latin alphabet No.1            | ISO-8859-1      |
| 8859part2                        | ISO/IEC 8859-2, Information technology - 8-bit single byte coded graphic character sets - Part 2 : Latin alphabet No.2            | ISO-8859-2      |
| 8859part3                        | ISO/IEC 8859-3, Information technology - 8-bit single byte coded graphic character sets - Part 3 : Latin alphabet No.3            | ISO-8859-3      |
| 8859part4                        | ISO/IEC 8859-4, Information technology - 8-bit single byte coded graphic character sets - Part 4 : Latin alphabet No.4            | ISO-8859-4      |
| 8859part5                        | ISO/IEC 8859-5, Information technology - 8-bit single byte coded graphic character sets - Part 5 : Latin/Cyrillic alphabet        | ISO-8859-5      |
| 8859part6                        | ISO/IEC 8859-6, Information technology - 8-bit single byte coded graphic character sets - Part 6 : Latin/Arabic alphabet          | ISO-8859-6      |
| 8859part7                        | ISO/IEC 8859-7, Information technology - 8-bit single byte coded graphic character sets - Part 7 : Latin/Greek alphabet           | ISO-8859-7      |
| 8859part8                        | ISO/IEC 8859-8, Information technology - 8-bit single byte coded graphic character sets - Part 8 : Latin/Hebrew alphabet          | ISO-8859-8      |
| 8859part9                        | ISO/IEC 8859-9, Information technology - 8-bit single byte coded graphic character sets - Part 9 : Latin alphabet No.5            | ISO-8859-9      |
| 8859part10                       | ISO/IEC 8859-10, Information technology - 8-bit single byte coded graphic character sets - Part 10 : Latin alphabet No.6          | ISO-8859-10     |
| 8859part11                       | ISO/IEC 8859-11, Information technology - 8-bit single byte coded graphic character sets - Part 11 : Latin/Thai alphabet          | ISO-8859-11     |
| 8859part13                       | ISO/IEC 8859-13, Information technology - 8-bit single byte coded graphic character sets - Part 13 : Latin alphabet No.7          | ISO-8859-13     |
| 8859part14                       | ISO/IEC 8859-14, Information technology - 8-bit single byte coded graphic character sets - Part 14 : Latin alphabet No.8 (Celtic) | ISO-8859-14     |
| 8859part15                       | ISO/IEC 8859-15, Information technology - 8-bit single byte coded graphic character sets - Part 15 : Latin alphabet No.9          | ISO-8859-15     |
| 8859part16                       | ISO/IEC 8859-16, Information technology - 8-bit single byte coded graphic character sets - Part 16 : Latin alphabet No.10         | ISO-8859-16     |
| *jis*                            | *japanese code set used for electronic transmission*                                                                              | *JIS\_Encoding* |
| shiftJIS                         | japanese code set used on MS-DOS machines                                                                                         | Shift\_JIS      |
| eucJP                            | japanese code set used on UNIX based machines                                                                                     | EUC-JP          |
| usAscii                          | United States ASCII code set (ISO 646 US)                                                                                         | US-ASCII        |
| *ebcdic*                         | *IBM mainframe code set*                                                                                                          | *IBM037*        |
| eucKR                            | Korean code set                                                                                                                   | EUC-KR          |
| big5                             | traditional Chinese code set used in Taiwan, Hong Kong of China and other areas                                                   | Big5            |
| GB2312                           | simplified Chinese code set                                                                                                       | GB2312          |

| Example                                                                                                                                                                                                                                     |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 \[\] a dcat:Dataset ;                                                                                                                                                                                                                        
                                                                                                                                                                                                                                              
 dcat:distribution \[ a dcat:Distribution ;                                                                                                                                                                                                   
                                                                                                                                                                                                                                              
 cnt:characterEncoding "UTF-8"^^xsd:string \] .                                                                                                                                                                                               
                                                                                                                                                                                                                                              
 \# Metadata on metadata in GeoDCAT-AP                                                                                                                                                                                                        
                                                                                                                                                                                                                                              
 \[\] a dcat:CatalogRecord ;                                                                                                                                                                                                                  
                                                                                                                                                                                                                                              
 cnt:characterEncoding "UTF-8"^^xsd:string.                                                                                                                                                                                                   |
| &lt;gmd:MD\_Metadata&gt;                                                                                                                                                                                                                    
                                                                                                                                                                                                                                              
 ...                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;!-- Metadata on metadata: metadata character set --&gt;                                                                                                                                                                                  
                                                                                                                                                                                                                                              
 &lt;gmd:characterSet&gt;                                                                                                                                                                                                                     
                                                                                                                                                                                                                                              
 &lt;MD\_CharacterSetCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#MD\_CharacterSetCode" codeListValue="utf8"&gt; UTF-8 &lt;/MD\_CharacterSetCode&gt;  
                                                                                                                                                                                                                                              
 &lt;/gmd:characterSet&gt;                                                                                                                                                                                                                    
                                                                                                                                                                                                                                              
 ...                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;!-- Resource metadata: dataset character set --&gt;                                                                                                                                                                                      
                                                                                                                                                                                                                                              
 &lt;gmd:identificationInfo&gt;                                                                                                                                                                                                               
                                                                                                                                                                                                                                              
 &lt;gmd:MD\_DataIdentification&gt;                                                                                                                                                                                                           
                                                                                                                                                                                                                                              
 ...                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;gmd:characterSet&gt;                                                                                                                                                                                                                     
                                                                                                                                                                                                                                              
 &lt;gmd:MD\_CharacterSetCode codeListValue="utf8" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#MD\_CharacterSetCode*"/&gt;                               
                                                                                                                                                                                                                                              
 &lt;/gmd:characterSet&gt;                                                                                                                                                                                                                    
                                                                                                                                                                                                                                              
 ...                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;/gmd:MD\_DataIdentification&gt;                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;/gmd:identificationInfo&gt;                                                                                                                                                                                                              
                                                                                                                                                                                                                                              
 ...                                                                                                                                                                                                                                          
                                                                                                                                                                                                                                              
 &lt;/gmd:MD\_Metadata&gt;                                                                                                                                                                                                                    |

<span id="_Ref417900366" class="anchor"><span id="_Toc437955449" class="anchor"><span id="_Toc447881069" class="anchor"></span></span></span>Encoding - \*Distribution format
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In both DCAT and DCAT-AP, this information is specified for the distribution(s) of a dataset, and not for the dataset itself.

Two properties are foreseen:

-   dcat:mediaType: to be used when the format corresponds to one of the media types registered by IANA \[IANA-MT\].

-   dct:format: to be used in all the other cases.

The same approach is used in GeoDCAT-AP for ISO 19115 / INSPIRE metadata.

In both cases, DCAT-AP recommends the use of the URI file type register \[MDR-FT\], operated by the Metadata Registry of the Publications Office of the EU, to specify formats/media types. However, this register does not include many of the formats/media types typically used for INSPIRE data – as, e.g., GML, shapefiles and raster files – which are available through the INSPIRE media type register \[INSPIRE-MT\].

The proposal is then to use the file type register of the Publications Office, if it includes the relevant format/media type, and the INSPIRE Media Types register otherwise.

| Example                                                                                       |
|-----------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                            
                                                                                                
 \[\] a dcat:Dataset ;                                                                          
                                                                                                
 dcat:distribution \[ a dcat:Distribution ;                                                     
                                                                                                
 dcat:mediaType &lt;*http://publications.europa.eu/resource/authority/file-type/TIFF*&gt; \] .  |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                  
                                                                                                
 &lt;gmd:MD\_Metadata&gt;                                                                       
                                                                                                
 ...                                                                                            
                                                                                                
 &lt;gmd:distributionInfo&gt;                                                                   
                                                                                                
 &lt;gmd:MD\_Distribution&gt;                                                                   
                                                                                                
 &lt;gmd:distributionFormat&gt;                                                                 
                                                                                                
 &lt;gmd:MD\_Format&gt;                                                                         
                                                                                                
 &lt;gmd:name&gt;                                                                               
                                                                                                
 &lt;gco:CharacterString&gt;GeoTIFF&lt;/gco:CharacterString&gt;                                 
                                                                                                
 &lt;/gmd:name&gt;                                                                              
                                                                                                
 &lt;gmd:version&gt;                                                                            
                                                                                                
 &lt;gco:CharacterString&gt;1.0&lt;/gco:CharacterString&gt;                                     
                                                                                                
 &lt;/gmd:version&gt;                                                                           
                                                                                                
 &lt;/gmd:MD\_Format&gt;                                                                        
                                                                                                
 &lt;/gmd:distributionFormat&gt;                                                                
                                                                                                
 ...                                                                                            
                                                                                                
 &lt;/gmd:MD\_Distribution&gt;                                                                  
                                                                                                
 &lt;/gmd:distributionInfo&gt;                                                                  
                                                                                                
 ...                                                                                            
                                                                                                
 &lt;/gmd:MD\_Metadata&gt;                                                                      |

 <span id="_Ref420451963" class="anchor"><span id="_Toc437955450" class="anchor"><span id="_Toc447881070" class="anchor"></span></span></span>Spatial representation type – \*Spatial representation type
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In DCAT-AP, no equivalent term is foreseen.

In ISO 19115, element “Spatial representation type” is meant mainly to describe the “method used to represent geographic information in the dataset”, by using a code list (see the table below).

The ADMS vocabulary includes a property, namely, adms:representationTechnique that could be used for this purpose. It is worth noting that, in the ADMS specification, adms:representationTechnique decribes a distribution, and not the dataset. Moreover, the ISO 19115 code list of spatial representation types might be in the future available as a URI register from the INSPIRE Registry.

Based on this, GeoDCAT-AP models this information by using property adms:representationTechnique, with the spatial representation type URIs that will be operated by the INSPIRE Registry.

This mapping is supported only in the extended profile of GeoDCAT-AP.

The spatial representation types defined in ISO 19115 are listed in the following table. It is important to note that, as stated in the INSPIRE Data Specifications, the only spatial representation types in scope of INSPIRE are the following ones: “vector”, “grid”, and “tin”.

| ISO 19115 - MD\_SpatialRepresenationTypeCode | Description                                                                                        | In scope of INSPIRE? |
|----------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------|
| vector                                       | vector data is used to represent geographic data                                                   | Yes                  |
| grid                                         | grid data is used to represent geographic data                                                     | Yes                  |
| textTable                                    | textual or tabular data is used to represent geographic data                                       | No                   |
| tin                                          | triangulated irregular network                                                                     | Yes                  |
| stereoModel                                  | three-dimensional view formed by the intersecting homologous rays of an overlapping pair of images | No                   |
| video                                        | scene from a video recording                                                                       | No                   |

| Example                                                                                                                                                                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                                            
 \[\] a dcat:Dataset ;                                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                            
 dcat:distribution \[ a dcat:Distribution                                                                                                                                                                                                                                                   
                                                                                                                                                                                                                                                                                            
 adms:represenationTechnique &lt;*http://inspire.ec.europa.eu/metadata-codelist/SpatialRepresentationTypeCode/vector*&gt;                                                                                                                                                                   
                                                                                                                                                                                                                                                                                            
 \] .                                                                                                                                                                                                                                                                                       |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                                                                                                              
                                                                                                                                                                                                                                                                                            
 &lt;gmd:spatialRepresentationType&gt;                                                                                                                                                                                                                                                      
                                                                                                                                                                                                                                                                                            
 &lt;gmd:MD\_SpatialRepresentationTypeCode codeListValue="vector" codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/gmxCodelists.xml\#MD\_SpatialRepresentationTypeCode*"&gt;vector&lt;/gmd:MD\_SpatialRepresentationTypeCode&gt;  
                                                                                                                                                                                                                                                                                            
 &lt;/gmd:spatialRepresentationType&gt;                                                                                                                                                                                                                                                     |

<span id="_Ref417901213" class="anchor"><span id="_Ref422248434" class="anchor"><span id="_Toc437955451" class="anchor"><span id="_Toc447881071" class="anchor"></span></span></span></span>Maintenance information - \*not in ISO 19115 core
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In ISO 19115, element “Maintenance information” is meant mainly to describe how frequently a resource is updated.

DCAT and DCAT-AP, the update frequency is expressed through dct:accrualPeriodicity, with the frequency codes defined in the Dublin Core Collection Description Frequency Vocabulary \[CLD-FREQ\], which can be partially mapped to the ones used in ISO 19115, as shown in the following table (the missing alignments are in bold). A similar mapping was added for the MDR Frequency Named Authority List \[MDR-FREQ\].

The ISO 19115 code list of maintenance frequency codes might be in the future available as a URI register from the INSPIRE Registry.

Based on this, maintenance frequency is modelled in GeoDCAT-AP by using dct:accrualPeriodicity with the MDR Frequency Named Authority List \[MDR-FREQ\].

For the frequency codes not covered by the MDR Frequency code list, the approach will be as follows:

-   In the core profile of GeoDCAT-AP these codes will be ignored:

-   The extended profile of GeoDCAT-AP will use the code list of ISO maintenance frequency codes operated by the INSPIRE Registry.

| ISO 19115 - MD\_MaintenanceFrequencyCode | Dublin Core Collection Description Frequency Vocabulary \[CLD-FREQ\] | MDR Frequency Named Authority List \[MDR-FREQ\] |
|------------------------------------------|----------------------------------------------------------------------|-------------------------------------------------|
| continual                                | continuous                                                           | UPDATE\_CONT / CONT                             |
| daily                                    | daily                                                                | DAILY                                           |
| weekly                                   | weekly                                                               | WEEKLY                                          |
| fortnightly                              | biweekly                                                             | BIWEEKLY                                        |
| monthly                                  | monthly                                                              | MONTHLY                                         |
| quarterly                                | quarterly                                                            | QUARTERLY                                       |
| biannually                               | semiannual                                                           | ANNUAL\_2                                       |
| annually                                 | annual                                                               | ANNUAL                                          |
| asNeeded                                 | -                                                                    | -                                               |
| Irregular                                | irregular                                                            | IRREG                                           |
| notPlanned                               | -                                                                    | -                                               |
| unknown                                  | -                                                                    | UNKNOWN                                         |
| -                                        | triennial                                                            | TRIENNIAL                                       |
| -                                        | biennial                                                             | BIENNIAL                                        |
| -                                        | threeTimesAYear                                                      | ANNUAL\_3                                       |
| -                                        | bimonthly                                                            | BIMONTHLY                                       |
| -                                        | semimonthly                                                          | MONTHLY\_2                                      |
| -                                        | threeTimesAMonth                                                     | MONTHLY\_3                                      |
| -                                        | semiweekly                                                           | WEEKLY\_2                                       |
| -                                        | threeTimesAWeek                                                      | WEEKLY\_3                                       |
| -                                        | -                                                                    | OTHER                                           |

| Example                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \# Resource metadata in GeoDCAT-AP                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                                                               
 \[\] a dcat:Dataset ;                                                                                                                                                                                                                                                         
                                                                                                                                                                                                                                                                               
 dct:accrualPeriodicity &lt;*http://publications.europa.eu/resource/authority/frequency/DAILY* &gt; .                                                                                                                                                                          |
| &lt;!-- Resource metadata in ISO19139 --&gt;                                                                                                                                                                                                                                 
                                                                                                                                                                                                                                                                               
 &lt;gmd:MD\_MaintenanceInformation&gt;                                                                                                                                                                                                                                        
                                                                                                                                                                                                                                                                               
 &lt;gmd:maintenanceAndUpdateFrequency gco:nilReason="missing"&gt;                                                                                                                                                                                                             
                                                                                                                                                                                                                                                                               
 &lt;gmd:MD\_MaintenanceFrequencyCode codeList="*http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO\_19139\_Schemas/resources/codelist/ML\_gmxCodelists.xml\#MD\_MaintenanceFrequencyCode*" codeListValue="daily"&gt;daily&lt;/gmd:MD\_MaintenanceFrequencyCode&gt;  
                                                                                                                                                                                                                                                                               
 &lt;/gmd:maintenanceAndUpdateFrequency&gt;                                                                                                                                                                                                                                    
                                                                                                                                                                                                                                                                               
 &lt;/gmd:MD\_MaintenanceInformation&gt;                                                                                                                                                                                                                                       |

<span id="_Ref424148634" class="anchor"><span id="_Toc437955452" class="anchor"><span id="_Toc447881072" class="anchor"></span></span></span>Comparison between INSPIRE and ISO 19115-1:2014
============================================================================================================================================================================================

In ISO 19115-1:2014 the concept of ‘Core metadata’ was removed; it was translated into a normative annex (Annex F) “Discovery metadata for geographic resources”. In the Annex F metadata elements for the discovery are listed in 2 tables:

-   the metadata elements to be used for discovery of geographic datasets and series are identified in F.1;

-   the metadata elements to be used for discovery of service resources are identified in F.2.

<span id="_Toc437955382" class="anchor"><span id="_Toc437955453" class="anchor"><span id="_Toc437955383" class="anchor"><span id="_Toc437955454" class="anchor"><span id="_Toc437955384" class="anchor"><span id="_Toc437955455" class="anchor"><span id="_Toc437955456" class="anchor"><span id="_Toc447881073" class="anchor"></span></span></span></span></span></span></span></span>Spatial dataset and spatial dataset series
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The table below compares the core requirements of ISO 19115:2003 (see Table 3 in 6.5 of ISO 19115:2003), the requirements of INSPIRE for spatial dataset and spatial dataset series as defined in the Implementing Rules for metadata and the discovery metadata for geographic datasets and series (see Table F.1 in annex F of ISO 19115-1:2014). For those last metadata elements in the last field of the table the path is indicated. For each element, in brackets the obligation/max occurrence (3rd field).

<span id="_Ref423966506" class="anchor"><span id="_Toc437955467" class="anchor"><span id="_Toc447881085" class="anchor"></span></span></span>Table : Metadata elements used for discovery of geographic datasets and series

|                                                                           |                                             |                                                                             |                                                                                                                                                                                                   |
|---------------------------------------------------------------------------|---------------------------------------------|-----------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ISO 19115 Core**                                                        | **INSPIRE Implementing Rules for Metadata** | **ISO 19115-1:2014 Discovery metadata for datasets and series (Table F.1)** | **ISO 19115-1:2014 Path**                                                                                                                                                                         |
| Dataset title (M)                                                         | Part B 1.1 Resource Title                   | Resource title (M/1)                                                        | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.citation&gt;CI\_Citation.title                                                                                                          |
| Dataset reference date (M)                                                | Part B 5 Temporal Reference                 | Resource reference date (O/N)                                               | MD\_Metadata.idenitificationInfo&gt;MD\_DataIdentification.citation&gt;CI\_Citation.date                                                                                                          |
| Dataset responsible party (O)                                             | Part B 9 Responsible organisation           | Resource point of contact (O/N)                                             | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.pointOf-Contact&gt;CI\_Responsibility                                                                                                   |
| Geographic location of the dataset (C)                                    | Part B 4.1 Geographic Bounding Box          | Geographic location (C/N)                                                   | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.extent&gt;EX\_Extent.geographicElement&gt;EX\_GeographicExtent&gt;EX\_GeographicBoundingBox –or- EX\_GeographicDescription)             |
| Dataset language (M)                                                      | Part B 1.7 Resource Language                | Resource language (C/N)                                                     | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.defaultLocale&gt;PT\_Locale                                                                                                             |
| Dataset character set (C)                                                 | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Dataset topic category (M)                                                | Part B 2.1 Topic Category                   | Resource topic category (C/N)                                               | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.topicCategory&gt;MD\_TopicCategoryCode                                                                                                  |
| Spatial resolution of the dataset (O)                                     | Part B 6.2 Spatial Resolution               | Spatial resolution (O/N)                                                    | MD\_Metadata.identificationInfo&gt;MD\_Identification.spatialResolution&gt;MD\_Resolution.equivalentScale MD\_Resolution.distance, MD\_Resolution.vertical, or MD\_Resolution.angularDistance, or 
                                                                                                                                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                         MD\_Resolution.levelOfDetail                                                                                                                                                                       |
| Abstract describing the dataset (M)                                       | Part B 1.2 Resource abstract                | Resource abstract (M/1)                                                     | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.abstract                                                                                                                                |
| Distribution format (O)                                                   | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Additional extent information for the dataset (vertical and temporal) (O) | Part B 5.1 Temporal extent                  | Extent information for the dataset (additional) (O/N)                       | MD\_Metadata.identificationInfo&gt;MD\_Identification.extent &gt; EX\_Extent&gt;EX\_TemporalExtent or EX\_VerticalExtent                                                                          |
| Spatial representation type (O)                                           | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Reference system (O)                                                      | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Lineage (O)                                                               | Part B 6.1 Lineage                          | Resource lineage (O/N)                                                      | MD\_Metadata&gt;resourceLineage&gt;LI\_Lineage.statement                                                                                                                                          |
| On-line resource (O)                                                      | Part B 1.4 Resource Locator                 | Resource on-line Link (O/N)                                                 | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.citation&gt;CI\_Citation.onlineResource&gt;CI\_OnlineResource                                                                           |
| Metadata file identifier (O)                                              | -                                           | Metadata reference information (O/1)                                        | MD\_Metadata.metadataIdentifier                                                                                                                                                                   |
| Metadata standard name (O)                                                | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Metadata standard version (O)                                             | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Metadata language (C)                                                     | Part B 10.3 Metadata Language               | -                                                                           | MD\_Metadata.defaultLocale&gt;PT\_Locale.language                                                                                                                                                 |
| Metadata character set (C)                                                | -                                           | -                                                                           |                                                                                                                                                                                                   |
| Metadata point of contact (M)                                             | Part B 10.1 Metadata point of contact       | Metadata point of contact (M/N)                                             | MD\_Metadata.contact&gt;CI\_Responsibility                                                                                                                                                        |
| Metadata date stamp (M)                                                   | Part B 10.2 Metadata Date                   | Metadata date stamp (M/N)                                                   | MD\_Metadata.dateInfo                                                                                                                                                                             |
| -                                                                         | Part B 1.3 Resource Type                    | Resource type (C/1)                                                         | MD\_Metadata.metadataScope&gt;MD\_Scope.resourceScope                                                                                                                                             |
|                                                                           | Part B 1.5 Unique Resource Identifier       | Resource identifier (O/N)                                                   | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification.citation&gt;CI\_Citation.identifier&gt;MD\_Identifier                                                                                   |
|                                                                           | Part B 3 Keyword                            | Keywords (O/N)                                                              | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification&gt;descriptiveKeywords&gt;MD\_Keywords                                                                                                  |
| -                                                                         | Part B 7 Conformity                         | -                                                                           | MD\_Metadata.dataQualityInfo&gt;DQ\_DataQuality.report&gt;DQ\_UsabilityElement.result&gt;DQ\_ConformanceResult                                                                                    |
| -                                                                         | Part B 8.1 Conditions for access and use    | Constraints on resource access and use (O/N)                                | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification&gt;MD\_Constraints.useLimitations                                                                                                       |
| -                                                                         | Part B 8.2 Limitations on public access     | Constraints on resource access and use (O/N)                                | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification&gt; MD\_LegalConstraints.accessConstraint and/or MD\_LegalConstraints.otherConstraint and/or MD\_SecurityConstraints.classification     |

<span id="_Toc437955457" class="anchor"><span id="_Toc447881074" class="anchor"></span></span>Services
------------------------------------------------------------------------------------------------------

The table below compares the core requirements of ISO 19115:2003 (see Table 3 in 6.5 of ISO 19115:2003), the requirements of INSPIRE for services as defined in the Implementing Rules for metadata and the discovery metadata for services (see Table F.2 in annex F of ISO 19115-1:2014). For those metadata elements in the last field of the table the path is indicated. For each element, in brackets the obligation/max occurrence (3<sup>rd</sup> field).

<span id="_Ref423966518" class="anchor"><span id="_Toc437955468" class="anchor"><span id="_Toc447881086" class="anchor"></span></span></span>Table : Metadata elements used for discovery of service resources

|                                                   |                                          |                                                                  |                                                                                                                                                                                               |
|---------------------------------------------------|------------------------------------------|------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ISO 19115 Core**                                | **INSPIRE**                              | **ISO 19115-1:2014 Discovery metadata for services (Table F.2)** | **Path ISO 19115-1:2014**                                                                                                                                                                     |
| Dataset title (M)                                 | Part B 1.1 Resource Title                | Service title (M/1)                                              | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.citation&gt;CI\_Citation.title                                                                                                   |
| Dataset reference date (M)                        | Part B 5 Temporal Reference              | Reference date (O/1)                                             | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.citation&gt;CI\_Citation.date                                                                                                    |
| Dataset responsible party (O)                     | Part B 9 Responsible organisation        | Responsible party (O/N)                                          | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.pointOfContact&gt;CI\_Responsibility                                                                                             |
| Geographic location of the dataset (C)            | **-**                                    | Geographic location (M/1)                                        | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.extent&gt;EX\_Extent.geographicElement &gt; EX\_GeographicExtent&gt;EX\_GeographicBoundingBox–or- EX\_GeographicDescription      |
| -                                                 | Part B 4.1 Geographic Bounding Box       | -                                                                |                                                                                                                                                                                               |
| Dataset language (M)                              | -                                        | -                                                                |                                                                                                                                                                                               |
| Dataset character set (C)                         | -                                        | -                                                                |                                                                                                                                                                                               |
| Dataset topic category (M)                        | -                                        | Service topic category (O/N)                                     | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.topicCategory&gt;MD\_TopicCategoryCode                                                                                           |
| Spatial resolution of the dataset (O)             | Part B 6.2 Spatial Resolution            | -                                                                |                                                                                                                                                                                               |
| Abstract describing the dataset (M)               | Part B 1.2 Resource abstract             | Resource abstract (M/1)                                          | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.abstract                                                                                                                         |
| Distribution format (O)                           | -                                        | -                                                                |                                                                                                                                                                                               |
| Additional extent information for the dataset (O) | -                                        | -                                                                |                                                                                                                                                                                               |
| Spatial representation type (O)                   | -                                        | -                                                                |                                                                                                                                                                                               |
| Reference system (O)                              | -                                        | -                                                                |                                                                                                                                                                                               |
| Lineage (O)                                       | -                                        | -                                                                |                                                                                                                                                                                               |
| On-line resource (O)                              | Part B 1.4 Resource Locator              | On-line Link (O/N)                                               | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.citation&gt;CI\_Citation.onlineResource&gt;CI\_OnlineResource                                                                    |
| Metadata file identifier (O)                      | -                                        | Metadata reference information (O/1)                             | MD\_Metadata.metadataIdentifier                                                                                                                                                               |
| Metadata standard name (O)                        | -                                        | -                                                                |                                                                                                                                                                                               |
| Metadata standard version (O)                     | -                                        | -                                                                |                                                                                                                                                                                               |
| Metadata language (C)                             | Part B 10.3 Metadata Language            | -                                                                | MD\_Metadata.defaultLocale&gt;PT\_Locale.language                                                                                                                                             |
| Metadata character set (C)                        | -                                        | -                                                                |                                                                                                                                                                                               |
| Metadata point of contact (M)                     | Part B 10.1 Metadata point of contact    | Metadata point of contact (M/N)                                  | MD\_Metadata.contact&gt;CI\_Responsibility                                                                                                                                                    |
| Metadata date stamp (M)                           | Part B 10.2 Metadata Date                | Metadata date stamp (M/N)                                        | MD\_Metadata.dateInfo                                                                                                                                                                         |
| -                                                 | Part B 1.3 Resource Type                 | Resource type (M/1)                                              | MD\_Metadata.metadataScope&gt;MD\_Scope.resourceScope                                                                                                                                         |
| -                                                 | Part B 1.6 Coupled Resource              | Coupled Resource (C/N)                                           | MD\_Metadata&gt;SV\_ServiceIdentification.coupledResource&gt;SVCoupledResource                                                                                                                |
| -                                                 | Part B 2.2 Spatial Data Service Type     | -                                                                |                                                                                                                                                                                               |
|                                                   | Part B 3 Keyword                         | Keywords (O/N)                                                   | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification&gt;MD\_Keywords                                                                                                                  |
| -                                                 | Part B 7 Conformity                      | -                                                                | MD\_Metadata.dataQualityInfo&gt;DQ\_DataQuality.report&gt;DQ\_UsabilityElement.result&gt;DQ\_ConformanceResult                                                                                |
| -                                                 | Part B 8.1 Conditions for access and use | Constraints on access and use (O/N)                              | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification&gt;MD\_Constraints.useLimitations                                                                                                   |
| -                                                 | Part B 8.2 Limitations on public access  | Constraints on access and use (O/N)                              | MD\_Metadata.identificationInfo&gt;MD\_DataIdentification&gt; MD\_LegalConstraints.accessConstraint and/or MD\_LegalConstraints.otherConstraint and/or MD\_SecurityConstraints.classification |
| -                                                 | -                                        | Coupled resource type (C/1)                                      | MD\_Metadata&gt;SV\_ServiceIdentification.couplingType&gt;SV-CouplingType                                                                                                                     |
| -                                                 | -                                        | Resource identifier (O/N)                                        | MD\_Metadata.identificationInfo&gt;SV\_ServiceIdentification.citation&gt;CI\_Citation.identifier&gt;MD\_Identifier                                                                            |

[1] <http://publications.europa.eu/mdr/eurovoc/>

[2] European Commission – Joint Research Centre. INSPIRE Web site: <http://inspire.ec.europa.eu/>

[3] <https://webgate.ec.europa.eu/CITnet/stash/projects/ODCKAN/repos/iso-19139-to-dcat-ap/browse/documentation/Mappings.md>

[4] <https://webgate.ec.europa.eu/CITnet/stash/projects/ODCKAN/repos/iso-19139-to-dcat-ap/browse/documentation/HTTP-URIs.md>

[5] <https://open-data.europa.eu/>

[6] <http://www.europeandataportal.eu/>

[7] Please note that the Core Location Vocabulary does not restrict locn:geometry to bounding box geometries only.

[8] <http://www.iana.org/assignments/character-sets/>
