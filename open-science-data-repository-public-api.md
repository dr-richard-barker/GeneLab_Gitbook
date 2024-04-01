# Open Science Data Repository Public API

NASA OSDR provides a RESTful Application Programming Interface (API) to its full-text search, data file retrieval, and metadata retrieval capabilities. The API provides a choice of standard web output formats, either JavaScript Object Notation (JSON) or Hyper Text Markup Language (HTML), of query results. The Data File API returns metadata on data files associated with dataset(s), including the location of these files for download via https. The Metadata API returns entire sets of metadata for input study dataset accession numbers. The Search API can be used to search dataset metadata by keywords and/or metadata. It can also be used to provide search of three other omics databases: the National Institutes of Health (NIH) / National Center for Biotechnology Information's (NCBI) Gene Expression Omnibus (GEO); the European Bioinformatics Institute's (EBI) Proteomics Identification (PRIDE); the Argonne National Laboratory's (ANL) Metagenomics Rapid Annotations using Subsystems Technology (MG-RAST).

In addition to study datasets, NASA OSDR also hosts metadata for 7 other data types: experiments, payloads, subjects, biospecimens, missions, vehicles, and hardware. The API for these data types is listed separately and uniform throughout, to make for easy metadata exploration.

***

#### Contents:

* [**Study**](broken-reference)
  * [**Data File API**](broken-reference)
  * [**Metadata API**](broken-reference)
  * [**Search API**](broken-reference)
* [**Experiments, Missions, Payloads, Hardware, Vehicles, Subjects, Biospecimens**](broken-reference)
* [**API Requests with Python**](broken-reference)
* [**Resources**](broken-reference)

***

### Study <a href="#study" id="study"></a>

### Study Data File API <a href="#data" id="data"></a>

#### Syntax

https://osdr.nasa.gov/osdr/data/osd/files/{OSD\_STUDY\_IDs}/?page={CURRENT\_PAGE\_NUMBER}\&size={RESULTS\_PER\_PAGE}?all\_files={ALL\_FILES}

#### Returns: JSON-formatted response

| Parameters              | Data Type          | Notes                                                                                                                                                                              | Values                  | Required |
| ----------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | -------- |
| {OSD\_STUDY\_IDs}       | Integer or Decimal | Comma separated list with mixture of single OSD accession numbers and ranges. Use single decimal numbers to indicate a specific study version (Ex: 4.1 would be OSD-4, version 1). | ex. 87-95,137,153.2     | Yes      |
| {CURRENT\_PAGE\_NUMBER} | Integer            | Current page number in pagination                                                                                                                                                  | Starts from 0           | No       |
| {RESULTS\_PER\_PAGE}    | Integer            | Number of results returned per page in pagination                                                                                                                                  | Max 25 results per page | No       |
| {ALL\_FILES}            | Boolean            | Include hidden files. true to include invisible files; false to exclude. Default value is false.                                                                                   | true or false           | No       |

#### Example requests:

* Single study request using study accession number
  * [https://osdr.nasa.gov/osdr/data/osd/files/87](https://osdr.nasa.gov/osdr/data/osd/files/87)
* Multiple studies request using combination of range and comma separated list
  * [https://osdr.nasa.gov/osdr/data/osd/files/137,87-95,13,20-50](https://osdr.nasa.gov/osdr/data/osd/files/137,87-95,13,20-50)

#### Note:

The study\_files element in the JSON response has the remote\_url attribute, which can be used to obtain the specific download URL for the file by prefacing with the OSDR data server address, [https://osdr.nasa.gov](https://osdr.nasa.gov/) . In the example query/response below, the first study file for OSD-87 (version 1) study in the response below can be downloaded from [https://osdr.nasa.gov/geode-py/ws/studies/OSD-87/download?source=datamanager\&file=GLDS-87\_metadata\_Zanello\_STS135-ISA.zip](https://osdr.nasa.gov/geode-py/ws/studies/OSD-87/download?source=datamanager\&file=GLDS-87\_metadata\_Zanello\_STS135-ISA.zip)

#### Example Requests:

**Single Study Request:**

Example: [https://osdr.nasa.gov/osdr/data/osd/files/87.1](https://osdr.nasa.gov/osdr/data/osd/files/87.1)

**Response:**

```
{
  "hits": 1,
  "input": "87.1",
  "page_number": 1,
  "page_size": 25,
  "page_total": 1,
  "studies": {
    "OSD-87": {
      "file_count": 7,
      "study_files": [
        {
          "category": "Study Metadata Files",
          "date_created": 1516434676.433,
          "date_updated": "",
          "file_name": "GLDS-87_metadata_Zanello_STS135-ISA.zip",
          "file_size": 4809,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_metadata_Zanello_STS135-ISA.zip",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_14R_(Mouse430_2).CEL.gz",
          "file_size": 6374949,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_14R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_16R_(Mouse430_2).CEL.gz",
          "file_size": 6274393,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_16R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_20R_(Mouse430_2).CEL.gz",
          "file_size": 6384622,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_20R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_52R_(Mouse430_2).CEL.gz",
          "file_size": 6297226,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_52R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_54R_(Mouse430_2).CEL.gz",
          "file_size": 6017124,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_54R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_58R_(Mouse430_2).CEL.gz",
          "file_size": 6329707,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_58R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        }
      ]
    }
  },
  "success": true,
  "total_hits": 1,
  "valid_input": ["87"]
}        
    
```

**Multiple Study Data Files Request:**

Example: [https://osdr.nasa.gov/osdr/data/osd/files/137.1,86-87](https://osdr.nasa.gov/osdr/data/osd/files/137.1,86-87)

**Response:**

```
{
  "hits": 3,
  "input": "137.1,86-87",
  "page_number": 1,
  "page_size": 25,
  "page_total": 1,
  "studies": {
    "OSD-137": {
      "file_count": 39,
      "study_files": [
        {
          "category": "RNA-Seq Data",
          "date_created": 1506033836.839,
          "date_updated": "",
          "file_name": "GLDS-137_transcriptomics_RR3-BSL-B1.tar.gz",
          "file_size": 14879922202,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-137/download?source=datamanager&file=GLDS-137_transcriptomics_RR3-BSL-B1.tar.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "RNA-Seq Data",
          "date_created": 1506033836.839,
          "date_updated": "",
          "file_name": "GLDS-137_transcriptomics_RR3-BSL-B2.tar.gz",
          "file_size": 15103810246,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-137/download?source=datamanager&file=GLDS-137_transcriptomics_RR3-BSL-B2.tar.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        ...
        {
          "category": "Whole Genome Bisulfite Sequencing Data",
          "date_created": 1524338323.849,
          "date_updated": "",
          "file_name": "GLDS-137_epigenomics_RR3-GC-G7-LVR.tar",
          "file_size": 109839032320,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-137/download?source=datamanager&file=GLDS-137_epigenomics_RR3-GC-G7-LVR.tar",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Whole Genome Bisulfite Sequencing Data",
          "date_created": 1523353758.212,
          "date_updated": "",
          "file_name": "GLDS-137_epigenomics_RR3-BSL-B1-LVR.tar",
          "file_size": 73434449920,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-137/download?source=datamanager&file=GLDS-137_epigenomics_RR3-BSL-B1-LVR.tar",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        }
      ]
    },
    "OSD-86": {
      "file_count": 17,
      "study_files": [
        {
          "category": "Study Metadata Files",
          "date_created": 1600242553.708,
          "date_updated": 1600242553.708,
          "file_name": "GLDS-86_metadata_GSE65477-v1-ISA.zip",
          "file_size": 4904,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-86/download?source=datamanager&file=GLDS-86_metadata_GSE65477-v1-ISA.zip",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Whole Genome Bisulfite Sequencing Data",
          "date_created": 1506033835.554,
          "date_updated": "",
          "file_name": "GLDS-86_epigenomics_SRR1781971_1.fastq.gz",
          "file_size": 1438278406,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-86/download?source=datamanager&file=GLDS-86_epigenomics_SRR1781971_1.fastq.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        ...
        {
          "category": "Whole Genome Bisulfite Sequencing Data",
          "date_created": 1506033835.554,
          "date_updated": "",
          "file_name": "GLDS-86_epigenomics_SRR1781978_1.fastq.gz",
          "file_size": 3892512382,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-86/download?source=datamanager&file=GLDS-86_epigenomics_SRR1781978_1.fastq.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Whole Genome Bisulfite Sequencing Data",
          "date_created": 1506033835.554,
          "date_updated": "",
          "file_name": "GLDS-86_epigenomics_SRR1781978_2.fastq.gz",
          "file_size": 3851398439,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-86/download?source=datamanager&file=GLDS-86_epigenomics_SRR1781978_2.fastq.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        }
      ]
    },
    "OSD-87": {
      "file_count": 29,
      "study_files": [
        {
          "category": "Study Metadata Files",
          "date_created": 1601509296.578,
          "date_updated": 1601509296.578,
          "file_name": "GLDS-87_metadata_Zanello_STS135-ISA.zip",
          "file_size": 6504,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_metadata_Zanello_STS135-ISA.zip",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "Microarray Data Files",
          "date_created": 1506033834.109,
          "date_updated": "",
          "file_name": "GLDS-87_microarray_14R_(Mouse430_2).CEL.gz",
          "file_size": 6374949,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_microarray_14R_(Mouse430_2).CEL.gz",
          "restricted": false,
          "subcategory": "",
          "subdirectory": "",
          "visible": true
        },
        ...
        {
          "category": "GeneLab Processed Microarray Data Files",
          "date_created": 1582096720.619,
          "date_updated": 1582096720.619,
          "file_name": "GLDS-87_array_Mmus_C57-6CR_RTN_FLT_Rep3_58R_raw.CEL.gz",
          "file_size": 6413259,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_array_Mmus_C57-6CR_RTN_FLT_Rep3_58R_raw.CEL.gz",
          "restricted": false,
          "subcategory": "Raw Data",
          "subdirectory": "",
          "visible": true
        },
        {
          "category": "GeneLab Processed Microarray Data Files",
          "date_created": 1582096720.185,
          "date_updated": 1582096720.185,
          "file_name": "GLDS-87_array_Mmus_C57-6CR_RTN_FLT_Rep2_54R_raw.CEL.gz",
          "file_size": 6083294,
          "organization": "genelab",
          "remote_url": "/geode-py/ws/studies/OSD-87/download?source=datamanager&file=GLDS-87_array_Mmus_C57-6CR_RTN_FLT_Rep2_54R_raw.CEL.gz",
          "restricted": false,
          "subcategory": "Raw Data",
          "subdirectory": "",
          "visible": true
        }
      ]
    }
  },
  "success": true,
  "total_hits": 3,
  "valid_input": ["137", "86", "87"]
}
    
```

#### Syntax

https://osdr.nasa.gov/osdr/data/osd/meta/{OSD\_STUDY\_ID}

| Parameters       | Data Type | Notes                         | Values      | Required |
| ---------------- | --------- | ----------------------------- | ----------- | -------- |
| {OSD\_STUDY\_ID} | Integer   | Single study accession number | Example: 87 | Yes      |

**Single Study Metadata Request:**

Example: [https://osdr.nasa.gov/osdr/data/osd/meta/137](https://osdr.nasa.gov/osdr/data/osd/meta/137)

#### Returns: JSON-formatted response

**Response:**

Note to save space some information has been ommitted with ellipsis (...)

```
{
  "hits": 1,
  "input": "137",
  "study": {
    "OSD-137": {
      "additionalInformation": {
        "assays": {
          "a_OSD-137_dna-methylation-profiling_whole-genome-bisulfite-sequencing_illumina-txt": {
            "header": [...],
            "raw": [...],
            "table": [...]
          },
          "a_OSD-137_molecular-cellular-imaging_microscopy_pannoramic scan (3d histech)-txt": {...},
          "a_OSD-137_protein-expression-profiling_mass-spectrometry-txt": {...},
          "a_OSD-137_transcription-profiling_rna-sequencing-(rna-seq)-txt": {...}
        },
        "description": {
          "assays": [...],
          "factors": [...]
        },
        "ontologies": {...},
        "organisms": {
          "links": {
            "musmusculus": "<a target=\"_blank\" href=\"http://purl.bioontology.org/ontology/NCBITAXON/10090\" title=\"mouse <Mus musculus>\" source=\"NCBITAXON\">Mus musculus </a>"
          },
          "ontologies": {
            "musmusculus": {...}
          }
        },
        "samples": {...}
      },
      "comments": [],
      "ontologySourceReferences": [...],
      "people": [],
      "publications": [],
      "studies": [
        {
          "assays": [...],
          "characteristicCategories": [...],
          "comments": [
            {
              "name": "Acknowledgments",
              "value": "Funding for sample processing and sequencing was provided to the GeneLab project by the NASA Space Biology Program Office, Space Life and Physical Sciences Research and Applications Division. Samples from the RR-3 experiment were provided to GeneLab through the Biospecimen Sharing Plan of the NASA Life Sciences Data Archive. We would like to acknowledge the NASA Biospecimen Sharing Program (BSP) for their expertise and efforts in coordinating and collecting all the samples in this study."
            },
            { "name": "DOI", "value": "10.26030/9k6w-4c28" },
            { "name": "Data Source Accession", "value": "" },
            { "name": "Data Source Link", "value": "" },
            { "name": "Experiment Platform", "value": "Rodent Habitat" },
            { "name": "Flight Program", "value": "International Space Station (ISS)" },
            {
              "name": "Funding",
              "value": "This investigation was funded by the ISS National Lab, the NASA Space Biology Program Office, Space Life and Physical Sciences Research and Applications Division and additional funding from the International Space Station Research Integration Office to the Space Biology GeneLab Project"
            },
            { "name": "Identifiers", "value": "" },
            { "name": "Managing NASA Center", "value": "Ames Research Center (ARC)" },
            { "name": "Mission End", "value": "05/11/2016" },
            { "name": "Mission Link", "value": "https://osdr.nasa.gov/bio/repo/data/missions/SpaceX-8" },
            { "name": "Mission Name", "value": "SpaceX-8" },
            { "name": "Mission Start", "value": "04/08/2016" },
            { "name": "Project Identifier", "value": "RR-3" },
            { "name": "Project Link", "value": "https://lsda.jsc.nasa.gov/Experiment/exper/13961" },
            { "name": "Project Title", "value": "Rodent Research 3 (RR3)" },
            { "name": "Project Type", "value": "Spaceflight Study" },
            { "name": "Space Program", "value": "NASA" },
            { "name": "Study Grant Number", "value": "" }
          ],
          "description": "The Rodent Research-3 (RR-3) mission was sponsored by the pharmaceutical company Eli Lilly and Co. and the Center for the Advancement of Science in Space to study the effectiveness of a potential countermeasure for the loss of muscle and bone mass that occurs during spaceflight. Twenty BALB/c, 12-weeks old female mice (ten controls and ten treated) were flown to the ISS and housed in the Rodent Habitat for 39-42 days. Twenty mice of similar age, sex and strain were used for ground controls housed in identical hardware and matching ISS environmental conditions. Basal controls were housed in standard vivarium cages. Spaceflight, ground controls and basal groups had blood collected, then were euthanized, had one hind limb removed, and finally whole carcasses were stored at -80 C until dissection. All mice in this data set received only the control/sham injection.",
          "factors": [...],
          "identifier": "OSD-137",
          "materials": {...},
          "people": [...],
          "processSequence": [...],
          "protocols": [...],
          "publicReleaseDate": "28-Aug-2017",
          "publications": [
            {
              "authorList": "Beheshti A, Chakravarty K, Fogle H, Fazelinia H, Silveira WAD, Boyko V, Lai Polo S, Saravia-Butler AM, Hardiman G, Taylor D, Galazka JM, Costes SV",
              "comments": [],
              "doi": "10.1038/s41598-019-55869-2",
              "pubMedID": "31844325",
              "status": {
                "@id": "LmdAvi3HYaAIgsfwpY1sWHGrDR5sHm3luQJDg1Ay",
                "annotationValue": "published",
                "comments": [],
                "termAccession": "http://www.ebi.ac.uk/efo/EFO_0001796",
                "termSource": "EFO"
              },
              "title": "Multi-omics analysis of multiple missions to space reveal a theme of lipid dysregulation in mouse liver"
            }
          ],
          "studyDesignDescriptors": [...],
          "submissionDate": "04-Aug-2017",
          "title": "Rodent Research-3-CASIS: Mouse liver transcriptomic, proteomic, epigenomic and histology data",
          "unitCategories": [...]
        }
      ],
      "version": 8
    }
  },
  "success": true
}
    
```

### Study Dataset Search API <a href="#search" id="search"></a>

#### Syntax 1 (returns JSON response)

https://osdr.nasa.gov/osdr/data/search?\<PARAMETER-LIST>

| parameters | definition                  | values                                                                                                                                                                                            |
| ---------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| term       | search keyword              | string                                                                                                                                                                                            |
| from       | starting page               | integer (single value)                                                                                                                                                                            |
| size       | search result display count | integer (single value)                                                                                                                                                                            |
| type       | datasource                  | cgene , nih\_geo, ebi\_pride, mg\_rast (accepts multiple value separated by comma separated)                                                                                                      |
| sort       | sort field                  | string (Field Name)                                                                                                                                                                               |
| order      | sort order                  | ASC - ascending order; DESC - descending order                                                                                                                                                    |
| ffield     | filter field                | string (should always be pared with fvalue); append .raw to the end of the field to use the exact match index; see table below for possible filter field values and example filter value pairings |
| fvalue     | filter value                | string (should always be pared with ffield)                                                                                                                                                       |

| Filter Field (Case Sensitive)   | Example Filter Value                                                                            |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| Accession                       | OSD-4                                                                                           |
| Acknowledgments                 | NASA JPL                                                                                        |
| Authoritative Source URL        | OSD-4                                                                                           |
| Data Source Accession           | GSE18388                                                                                        |
| Data Source Type                | cgene                                                                                           |
| Experiment Platform             | Animal Enclosure Module                                                                         |
| Flight Program                  | Shuttle                                                                                         |
| links                           | GPL13112                                                                                        |
| Managing NASA Center            | Ames Research Center                                                                            |
| Material Type                   | thymus                                                                                          |
| organism                        | Mus musculus                                                                                    |
| Project Identifier              | NNA04CC97G                                                                                      |
| Project Link                    | https://taskbook.nasaprs.com/tbp/index.cfm?action=public\_query\_taskbook\_content\&TASKID=7191 |
| Project Title                   | Vector-Averaged Gravity                                                                         |
| Project Type                    | Spaceflight                                                                                     |
| Space Program                   | NASA                                                                                            |
| Study Assay Measurement Type    | transcription profiling                                                                         |
| Study Assay Technology Platform | Affymetrix                                                                                      |
| Study Assay Technology Type     | DNA microarray                                                                                  |
| Study Description               | Murine Thymus Tissue                                                                            |
| Study Factor Name               | Spaceflight                                                                                     |
| Study Factor Type               | Space Flight                                                                                    |
| Study Funding Agency            | NNA04CC97G                                                                                      |
| Study Identifier                | OSD-4                                                                                           |
| Study Protocol Description      | thymus tissue                                                                                   |
| Study Protocol Name             | sample collection                                                                               |
| Study Protocol Type             | sample collection                                                                               |
| Study Public Release Date       | 1268179200                                                                                      |
| Study Publication Author List   | Gruener R                                                                                       |
| Study Publication Title         | spaceflown murine thymus tissue                                                                 |
| Study Title                     | Space-flown Murine Thymus Tissue                                                                |

POST and GET requests accept the URL encoded name/value pairs for submission

Examples:

* [https://osdr.nasa.gov/osdr/data/search?term=space\&from=0\&type=cgene,nih\_geo\_gse\&ffield=links\&fvalue=GPL16417\&ffield=Data%20Source%20Accession.raw\&fvalue=GSE82255](https://osdr.nasa.gov/osdr/data/search?term=space\&from=0\&type=cgene,nih\_geo\_gse\&ffield=links\&fvalue=GPL16417\&ffield=Data%20Source%20Accession.raw\&fvalue=GSE82255)
* [https://osdr.nasa.gov/osdr/data/search?ffield=organism\&fvalue=Homo%20sapiens\&ffield=Study%20Assay%20Technology%20Type\&fvalue=RNA%20Sequencing](https://osdr.nasa.gov/osdr/data/search?ffield=organism\&fvalue=Homo%20sapiens\&ffield=Study%20Assay%20Technology%20Type\&fvalue=RNA%20Sequencing)

#### Syntax 2 (returns HTML response):

Format: https://osdr.nasa.gov/bio/repo/search?q=\<SEARCH-TERMS>\&data\_source=\<DATA-SOURCE>

| Parameters   | Values                                     | Usage                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------ | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SEARCH-TERMS | text                                       | <p>Any text to search for, can be augmented by the keywords:</p><ul><li>AND - ALL search terms must be present (default boolean search)</li><li>OR - ANY of your search terms can be present</li><li>NOT - exclude words from your search</li></ul><p>If no conjunctive or disjunctive operator specified, the default is "AND"</p>                                                                                                                              |
| DATA-SOURCE  | cgene, nih\_geo\_gse, ebi\_pride, mg\_rast | <ul><li>cgene - Search authoritative data records in NASA Open Science Data Repository</li><li>nih_geo_gse - Search authoritative data records in NIH Gene Expression Omnibus database</li><li>ebi_pride - Search authoritative data records in the European Bioinformatics Institute Proteomics Identification database</li><li>mg_rast - Search authoritative data records in the Metagenomic Rapid Annotations using Subsystems Technology database</li></ul> |

Examples:

* [https://osdr.nasa.gov/bio/repo/search?q=cancer\&data\_source=cgene](https://osdr.nasa.gov/bio/repo/search?q=cancer\&data\_source=cgene)
* [https://osdr.nasa.gov/osdr/bio/repo/search?q=mouse%20AND%20liver\&data\_source=cgene](https://osdr.nasa.gov/bio/repo/search?q=mouse%20AND%20liver\&data\_source=cgene)

### Experiments, Missions, Payloads, Hardware, Vehicles, Subjects, Biospecimens <a href="#other" id="other"></a>

### Format:

Experiments, Missions, Payloads, Hardware, Vehicles, Subjects, and Biospecimens follow the same API format. The "All" call returns a list of all objects within that data type, while the "Single" call returns an expanded version of a specific object. The endpoint for any single object can be selected from the "All" call. Some objects may include links to other objects within the API, such as a vehicle within a mission.

* Experiment:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/experiments](https://osdr.nasa.gov/geode-py/ws/api/experiments)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/experiment/ + identifier
* Mission:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/missions](https://osdr.nasa.gov/geode-py/ws/api/missions)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/mission/ + identifier
* Payload:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/payloads](https://osdr.nasa.gov/geode-py/ws/api/payloads)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/payload/ + identifier
* Hardware:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/hardware](https://osdr.nasa.gov/geode-py/ws/api/hardware)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/hardware/ + identifier
* Vehicle:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/vehicles](https://osdr.nasa.gov/geode-py/ws/api/vehicles)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/vehicle/ + identifier
* Subject:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/subjects](https://osdr.nasa.gov/geode-py/ws/api/subjects)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/subject/ + identifier
* Biospecimen:
  * All: [https://osdr.nasa.gov/geode-py/ws/api/biospecimens](https://osdr.nasa.gov/geode-py/ws/api/biospecimens)
  * Single: https://osdr.nasa.gov/geode-py/ws/api/biospecimen/ + identifier

### Examples:

#### Single Mission Call

[https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-12](https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-12)

**Response**

```
{
  "id": "6375b4f7313d542fb5edacaf",
  "identifier": "SpaceX-12",
  "identifierLowercase": "spacex-12",
  "esID": "XeBryYQB28eYt3lGVyVN",
  "aliases": ["SpX-12", "Increment 52/53", "CRS-12"],
  "startDate": "08/14/2017",
  "endDate": "09/17/2017",
  "files": [],
  "vehicle": { "vehicle": "https://osdr.nasa.gov/geode-py/ws/api/vehicle/Dragon" },
  "people": [
    {
      "institution": "Wake Forest School of Medicine",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda5c1",
        "firstName": "Jeffrey",
        "middleName": "Scott",
        "lastName": "Willey",
        "emailAddress": "jwilley@wakehealth.edu",
        "phone": "",
        "versionInfo": { "documentKey": "879a7f5eb83f436e88fbeeca1638899b", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "University of Florida",
      "roles": ["Co-Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda5eb",
        "firstName": "Brad",
        "middleName": "",
        "lastName": "Behnke",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "03fe55c410f54473b2df5e46ae8995ff", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Texas A&M University",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda5ec",
        "firstName": "David",
        "middleName": "",
        "lastName": "Zawieja",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "c871ffcaa74341f69d069174d1474819", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "NASA Ames Research Center (ARC)",
      "roles": ["Mission Integration and Operations Lead"],
      "person": {
        "id": "6375b4f6313d542fb5eda5a7",
        "firstName": "Cecilia",
        "middleName": "L.",
        "lastName": "Wigley",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "3011b2d648f54325bd510f5766cd74ca", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "NASA Ames Research Center (ARC)",
      "roles": ["Biospecimen Sharing Program (BSP) Lead"],
      "person": {
        "id": "6375b4f6313d542fb5eda65a",
        "firstName": "Rebecca",
        "middleName": "",
        "lastName": "Klotz",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "8c880d8fe6474be1b6ab98a476fe144a", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "NASA Ames Research Center (ARC)",
      "roles": ["Mission Scientist"],
      "person": {
        "id": "6375b4f6313d542fb5eda64d",
        "firstName": "Sungshin",
        "middleName": "",
        "lastName": "Choi",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "16374e18c88049bbbbaf90c88b63f809", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Florida State University",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda65e",
        "firstName": "Michael",
        "middleName": "",
        "lastName": "Delp",
        "emailAddress": "mdelp@fsu.edu",
        "phone": "",
        "versionInfo": { "documentKey": "a681490bdca94c79b98d5fd0a1c79962", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Loma LInda University",
      "roles": ["Co-Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda5be",
        "firstName": "Xiao Wen",
        "middleName": "",
        "lastName": "Mao",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "67df63fd7964413a9c61155b596e2a87", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "NASA Ames Research Center (ARC)",
      "roles": ["ARC Project Manager"],
      "person": {
        "id": "6375b4f6313d542fb5eda669",
        "firstName": "Janet",
        "middleName": "",
        "lastName": "Beegle",
        "emailAddress": "",
        "phone": "",
        "versionInfo": { "documentKey": "113febbfd77a4dab8313cc07d09a6c24", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "RIKEN Center for Integrative Medical Sciences",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda679",
        "firstName": "Hiroshi",
        "middleName": "",
        "lastName": "Ohno",
        "emailAddress": "",
        "phone": "+81-(0)45-503-9121",
        "versionInfo": { "documentKey": "03f15300b175436eafa1ed58e7754205", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Florida Gulf Coast University",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda684",
        "firstName": "Sherri",
        "middleName": "",
        "lastName": "Emer",
        "emailAddress": "semer@fgcu.edu",
        "phone": "239-745-4247",
        "versionInfo": { "documentKey": "a29f49cba0a5470e951d79962835d020", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Brock University",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda698",
        "firstName": "Val",
        "middleName": "Andrew",
        "lastName": "Fajardo",
        "emailAddress": "vfajardo@brocku.ca",
        "phone": "905-688-5550 ext. 4769",
        "versionInfo": { "documentKey": "7e64497572ba4b7683b5d578a9d03a34", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "University of Texas Rio Grande Valley",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda6ae",
        "firstName": "Upal",
        "middleName": "",
        "lastName": "Roy",
        "emailAddress": "upal.roy@utrgv.edu",
        "phone": "",
        "versionInfo": { "documentKey": "e14bc4fa65f74bb0b217d9176c9a03b5", "version": 1, "deleted": false }
      }
    },
    {
      "institution": "Indiana University School of Dentistry",
      "roles": ["Principal Investigator"],
      "person": {
        "id": "6375b4f6313d542fb5eda6af",
        "firstName": "Simone",
        "middleName": "",
        "lastName": "Duarte",
        "emailAddress": "siduarte@iu.edu",
        "phone": "585-330-6159",
        "versionInfo": { "documentKey": "c7a1f810f291422f9a44ef94bf4f9885", "version": 1, "deleted": false }
      }
    }
  ],
  "versionInfo": { "documentKey": "989cb8bb2add48f68fe7ec4e761704c6", "version": 1, "deleted": false },
  "parents": {
    "payload": [
      { "payload": "https://osdr.nasa.gov/geode-py/ws/api/payload/RR-9" },
      { "payload": "https://osdr.nasa.gov/geode-py/ws/api/payload/MHU-2" },
      { "payload": "https://osdr.nasa.gov/geode-py/ws/api/payload/RR-9_BSP" },
      { "payload": "https://osdr.nasa.gov/geode-py/ws/api/payload/BRIC-22" }
    ],
    "experiment": [{ "experiment": "https://osdr.nasa.gov/geode-py/ws/api/experiment/OS-140" }],
    "GLDS_Study": [
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-488" },
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-660" },
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-654" },
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-663" },
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-662" },
      { "GLDS_Study": "https://osdr.nasa.gov/osdr/data/osd/meta/OSD-321" }
    ]
  }
}    
  
```

#### Single Vehicle Call

From the above example, we can see a vehicle endpoint which directs us to the vehicle linked to SpaceX-12.

[https://osdr.nasa.gov/geode-py/ws/api/vehicle/Dragon](https://osdr.nasa.gov/geode-py/ws/api/vehicle/Dragon)

**Response**

```
{
  "id": "6375b4f8313d542fb5edbdfb",
  "identifier": "Dragon",
  "identifierLowercase": "dragon",
  "esID": "_uBzyYQB28eYt3lGm4k7",
  "files": [
    {
      "id": "6375b4f6313d542fb5edab7e",
      "fullPath": "DAP Drobo/RodentResearch/RR01/EnvironmentalMonitoring_Rearranged/ISS_ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 1 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\nIncluded in this series:\n1. A single file that combines the ISS cabin and ISSES chamber data. \"SP\" values are the set point from the ISS cabin near the rodent habitats and \"PV\" values are actual conditions in the simulation chambers. Data readings are every 5 minutes from 9/20/14 to just before midnight on 10/31/2014. (cabin_ISSES_ch3_RR1.xlsx)\n- Parameters:\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nCarbon dioxide (parts per million)\nThe status (On or Off) of Lights 1-3\n2. Raw and consolidated data files from two sensors on the International Space Station that were estimated to be nearest the rodent habitats in the lab module. Ambient temperature was collected for duration of the mission. (cabin_ISS_sto_Lab)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edab80",
      "fullPath": "DAP Drobo/RodentResearch/RR01/EnvironmentalMonitoring_Rearranged/VehicleData_SpX04_RR-1_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 1 mission data collection contains environmental, acoustics, vibrations, and acceleration data that pertain to the SpaceX CRS-21 Dragon cargo vehicle during ascent as it carried the Rodent Research payload to the International Space Station. \nThis dataset includes raw and reduced acceleration, carbon dioxide, oxygen, temperature, relative humidity, and pressure data for the pressurized cargo cabin environment; graphed acoustics and vibration data from the post flight report; a reference key for the raw data; a sensor location diagram for the Dragon capsule; and a cargo environments instrumentation plan for the Dragon capsule and Falcon 9 launch vehicle. \nParameters\nDragon cabin pressure (psia)\nPartial pressure of oxygen and carbon dioxide (psia)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nBody accelerations (m/s^2)\nAcoustics (decibels / hertz)\nVibrations (PSD (g^2Hz) / Hz)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edab8e",
      "fullPath": "DAP Drobo/RodentResearch/RR02/EnvironmentalMonitoring/VehicleData_SpX6_RR02_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 2 mission data collection contains environmental monitoring, acceleration, acoustics, and vibration data for the experiment while it was carried aboard the SpaceX-6 Dragon spacecraft.\nThe SpaceX6_Data directory contains datasets collected from the Dragon spacecraft. Included within are Dragon sensor locations and temperature and humidity data collected from loggers within the flight and ground transporters (SN 209 and SN 210). \nThe SpX-6_LaunchData, SpX-6_ProcessedFlightData and SpX-6_ReturnData subdirectories include sensor readings of environmental conditions in the cabin of the spacecraft (i.e. relative humidity, pressure, temperature, carbon dioxide, and oxygen concentration), as well as cabin acceleration, acoustic noise levels, and vibration loads during launch and ascent.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edab93",
      "fullPath": "DAP Drobo/RodentResearch/RR03/EnvironmentalMonitoring/ISS_ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 3 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\n- Parameters: \nTemperature (degrees Celsius)\nRelative humidity (percentage)\nCarbon dioxide (parts per million)\nISS Cabin Only: partial oxygen pressure raw and plotted data. Raw data are in one second intervals\n\"SP\" values are the set point from the ISS cabin near the rodent habitats and \"PV\" values are actual conditions in the simulation chambers.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabad",
      "fullPath": "DAP Drobo/RodentResearch/RR09/EnvironmentalMonitoring/VehicleData_SpaceX12_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 9 mission data collection contains environmental, acoustics, vibrations, and acceleration data that pertain to the SpaceX CRS-12 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth. \nThe following raw acceleration and pressurized cargo environment data are included (CSV):\n- A reference document for the data collection\n- For ascent: Dragon body acceleration (m/s^2) values\n- For ascent and descent: cabin pressure (psia), temperature readings from cabin air and duct sensors (degrees Celsius), relative humidity readings from cabin air and duct sensors (percent RH), partial pressure of carbon dioxide (psia), and partial pressure of oxygen (psia)\nThe following summarized data are included (PDF):\nA SpaceX post flight report entitled \"Dragon 1-14 (CRS-12) Final Report (Revision 1.0, November 8, 2017)\" has summarized data plots for the cargo hold temperature, relative humidity, partial pressure of oxygen and carbon dioxide throughout the mission as well as graphs for pressurized cargo vibration for ascent, acoustics for ascent and return, and cargo shock environments on reentry.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabb0",
      "fullPath": "DAP Drobo/RodentResearch/RR01/eclss_sensorlocations_dragon.pdf",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This document provides a diagram showing environmental monitoring sensor locations in the SpaceX CRS Dragon cabin and the corresponding headers in the data files. The diagram was provided by SpaceX for Rodent Research 1 and the data headers for temperature and pressure values subsequently changed. This document provides a crosswalk for later data files.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabb4",
      "fullPath": "DAP Drobo/RodentResearch/RR04/EnvironmentalMonitoring/VehicleData_SpaceX10_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 4 mission data collection contains environmental and acceleration data pertaining to the SpaceX CRS-10 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nThe following parameters are included for ascent and return:\nDragon cabin pressure (psia)\nBody accelerations (m/s^2)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nPartial pressure of oxygen and carbon dioxide (psia)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabb5",
      "fullPath": "DAP Drobo/RodentResearch/RR05/EnvironmentalMonitoring/VehicleData_SpaceX11_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 5 mission data collection contains environmental, acoustics, vibrations, and acceleration data pertaining to the SpaceX CRS-11 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth.\u00a0\nThe following raw data are included for ascent and return:\n   - Dragon cabin pressure (psia)\n   - Body accelerations (m/s^2)\n   - Temperature (degrees Celsius)\n   - Relative humidity (percentage)\n   - Partial pressure of oxygen and carbon dioxide (psia)\nThe following plotted data are included: \n   - Vibrations (ascent)\n   - Acoustics (launch and reentry)\n   - Cabin environment (entire mission): Pressure, relative humidity, temperature, partial pressure (oxygen and carbon dioxide)\nDate ranges:\nAscent: June 3-9, 2017\nReturn: July 1-3, 2017",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabb6",
      "fullPath": "DAP Drobo/RodentResearch/RR03/EnvironmentalMonitoring/VehicleData_SpaceX8_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 3 mission data collection contains environmental and acceleration data pertaining to the SpaceX CRS-8 Dragon vehicle as it carried the Rodent Research payload to the International Space Station.\nThe following parameters are included for ascent:\nDragon cabin pressure (psia)\nBody accelerations (m/s^2)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nPartial pressure of oxygen and carbon dioxide (psia)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabba",
      "fullPath": "DAP Drobo/RodentResearch/RR06/EnvironmentalMonitoring/VehicleData_SpaceX13-14_RR06_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of\u00a0the Rodent Research 6 mission data collection contains environmental and acceleration data that pertain to the SpaceX CRS-13 Dragon spacecraft as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nThe following parameters are included for ascent and return:\nDragon cabin pressure (psia)\nBody accelerations (m/s^2)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nPartial pressure of oxygen and carbon dioxide (psia)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabd1",
      "fullPath": "DAP Drobo/RodentResearch/RR08/EnvironmentalMonitoring/VehicleData_SpaceX16_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of\u00a0the Rodent Research 8 mission data collection contains environmental and acceleration data that pertain to the SpaceX CRS-16 Dragon spacecraft as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nDragon cabin pressure (psia)\nBody accelerations (m/s^2)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nPartial pressure of oxygen and carbon dioxide (psia)\nDate range of materials:\nDecember 4-9, 2018 (Ascent)\nJanuary 13-14, 2019 (Return)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabde",
      "fullPath": "DAP Drobo/RodentResearch/RR07/EnvironmentalMonitoring/VehicleData_SpaceX15_RR07_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 7 mission data collection contains environmental, acoustics, vibrations, and acceleration data that pertain to the SpaceX CRS-15 Dragon vehicle as it carried the Rodent Research payload to the International Space Station.\nThe following raw data are included for ascent (XLSX):\n- Dragon body acceleration (m/s^2)\n- Pressurized cabin: pressure (psia), temperature readings from cabin air and duct sensors (degrees Celsius), relative humidity readings from cabin air and duct sensors (percent RH), partial pressure of carbon dioxide (psia), and partial pressure of oxygen (psia). 35 readings per second.\nThe following summarized data are included in excerpts from the post flight report procuded by SpaceX (PDF/PPTX):\n- Dragon acoustics and random vibrations (plotted).\n(Note: The PDF and PPTX formats contain the same post flight report. The PPTX file was retained so that users can enlarge individual charts)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabdf",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR017/EnvironmentalMonitoring/VehicleData_SpX18_RR17_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of\u00a0the Rodent Research 17 mission data collection contains vehicle cabin environment and acceleration data for the SpaceX CRS-18 Dragon spacecraft as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nThe following raw data are included:\n- Dragon capsule body acceleration (m/s^2)\n- Dragon cabin environment, including temperature (degrees Celsius), relative humidity (percentage), pressure (psia), and partial pressure of oxygen and carbon dioxide (psia)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabe5",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR019/EnvironmentalMonitoring/VehicleData_SpX19_RR19_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 19 mission data collection contains vehicle cabin environment and acceleration data for the SpaceX CRS-19 Dragon spacecraft as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nDate range is 12/3/2019 - 1/7/2020 (GMT 337 2019 - 007 2020)\n   Late load:12/3-5, 2019\n   Ascent: 12/5-8, 2019\n   Berthed: 12/8-12, 2019\n   Return: 1/5-7, 2020\nThe following raw data are included for ascent and return: \nChannel 1 - Cabin air temperature (degrees Celsius)\nChannel 2 - Relative humidity (percentage)\nChannel 3 - Cabin pressure (psia)\nChannel 4 - Partial pressure of oxygen (psia)\nChannel 5 - Partial pressure of carbon dioxide (psia)\nChannel 6 - Dragon body acceleration (m/s^2)\nIncluded are the original dataset with UNIX timestamps and a copy dataset with the UNIX timestamps converted to GMT. The former is expressed to fractions of a second and the latter is in whole seconds.\nUNIX Date and Time conversion formula provided by SpaceX: \n-  =(TIME/86400+DATE(1970,1,1)) and format as time",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabf7",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR010/EnvironmentalMonitoring/VehicleData_SpX21_RR10_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 10 mission data collection contains atmospheric and acceleration data for the SpaceX CRS-21 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nAscent date range: December 6-7, 2020 (DOY 341-342)\nReturn date range: January 12-14, 2021 (DOY 012-014)\nThe following raw acceleration and pressurized cargo environment data are included (CSV).\nFor ascent and return: Dragon body acceleration (m/s^2), cabin pressure (psia), temperature readings from cabin air and duct sensors (degrees Celsius), relative humidity readings from cabin air and duct sensors (percent RH), partial pressure of carbon dioxide (psia), and partial pressure of oxygen (psia); summary graphs of all parameters.\nA reference document defining the parameters was not provided.\nSummarized Datasets\nGraphed data relating to Dragon pressurized cargo cabin environmental conditions are included for these parameters: temperature, relative humidity, partial pressure of oxygen and carbon dioxide, pressure, acoustics, and vibrations. The data are extracted from a SpaceX report entitled \"Dragon CRS-21 Post-Mission Data Review: Mission Management/Cargo.\" Date ranges span from late load on December 4, 2020 through return on January 14, 2021. \nFor most, the data graphs are presented in the context of required limits. Specifics include: \n- Late load install through launch, December 4-7, 2020: Dragon cabin temperature, relative humidity, partial pressure of oxygen, partial pressure of carbon dioxide, and cabin pressure.\n- Launch through docking with ISS, undated: Dragon cabin temperature, humidity, and pressure\n- Expected trends throughout mission, undated: Partial pressure of oxygen and carbon dioxide\n- Ascent random vibrations\n- Ascent and reentry acoustics",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edabf8",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR023/EnvironmentalMonitoring/VehicleData_SpX21_RR23_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 23 mission data collection contains atmospheric and acceleration data for the SpaceX CRS-21 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth.\nAscent date range: December 6-7, 2020 (DOY 341-342)\nReturn date range: January 12-14, 2021 (DOY 012-014)\n\nThe following raw acceleration and pressurized cargo environment data are included for ascent and return (CSV): \nDragon body acceleration (m/s^2), cabin pressure (psia), temperature readings from cabin air and duct sensors (degrees Celsius), relative humidity readings from cabin air and duct sensors (percent RH), partial pressure of carbon dioxide (psia), and partial pressure of oxygen (psia); summary graphs of all parameters.\nSummarized Datasets\nGraphed data relating to Dragon pressurized cargo cabin environmental conditions are included for these parameters: temperature, relative humidity, partial pressure of oxygen and carbon dioxide, pressure, acoustics, and vibrations. The data are extracted from a SpaceX report entitled \"Dragon CRS-21 Post-Mission Data Review: Mission Management/Cargo.\" Date ranges span from late load on December 4, 2020 through return on January 14, 2021.\nFor most, the data graphs are presented in the context of required limits. Specifics include: \n- Late load install through launch, December 4-7, 2020: Dragon cabin temperature, relative humidity, partial pressure of oxygen, partial pressure of carbon dioxide, and cabin pressure.\n- Launch through docking with ISS, undated: Dragon cabin temperature, humidity, and pressure\n- Expected trends throughout mission, undated: Partial pressure of oxygen and carbon dioxide\n- Ascent random vibrations\n- Ascent and reentry acoustics\nUnits of measure used:\nTemperature, degrees Celsius\nRelative humidity, percentage \nPressure, pounds per square inch absolute\nPartial pressure of oxygen, pounds per square inch absolute\nPartial pressure of carbon dioxide, millimeters of mercury\nRandom vibrations, power spectral density g^2/Hz\nAcoustics, sound pressure level (decibels relative to reference value ref20E-6 Pa)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac08",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR018/EnvironmentalMonitoring/VehicleData_SpX24_RR18_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 18 data collection contains atmospheric and acceleration data for the SpaceX CRS-24 Dragon vehicle as it carried the Rodent Research payload to the International Space Station and back down to Earth.\n\nRaw Datasets -- still need reference doc from SpX defining all parameters \n\nAscent date range: December XX, 2021 (DOY XX)\nReturn date range: XX XX, 2022 (DOY XX)\n\nThe following raw acceleration and pressurized cargo environment data are included (CSV).\n\nFor ascent and return: Dragon body acceleration (m/s^2), cabin pressure (psia), temperature readings from cabin air and duct sensors (degrees Celsius), relative humidity readings from cabin air and duct sensors (percent RH), partial pressure of carbon dioxide (psia), and partial pressure of oxygen (psia); summary graphs of all parameters.\n\nA reference document defining the parameters were not defined by the submitter).\n\nSummarized Datasets\nGraphed data relating to Dragon pressurized cargo cabin environmental conditions are included for these parameters: temperature, relative humidity, partial pressure of oxygen and carbon dioxide, pressure, acoustics, and vibrations. The data are extracted from a SpaceX report entitled Dragon CRS-21 Post-Mission Data Review: Mission Management/Cargo. Date ranges span from late load on XX 2021 through return on XX 2022. \n\nFor most, the data graphs are presented in the context of required limits. Specifics include: \n- Late load install through launch, December XX, 2021: Dragon cabin temperature, relative humidity, partial pressure of oxygen, partial pressure of carbon dioxide, and cabin pressure.\n- Launch through docking with ISS, undated: Dragon cabin temperature, humidity, and pressure\n- Expected trends throughout mission, undated: Partial pressure of oxygen and carbon dioxide\n- Ascent random vibrations\n- Ascent and reentry acoustics",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac0c",
      "fullPath": "DAP Drobo/RodentResearch/RR04/EnvironmentalMonitoring/cabin_ISSES_ch2-3_RR04.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 4 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin ground simulation chamber (ISSES) at KSC.\n- Parameters: \nTemperature (degrees Celsius); has a -2C offset = 20C is actually 22C\nRelative humidity (percentage)\nCarbon dioxide (parts per million)\n\"SP\" values are the set point from the ISS cabin near the rodent habitats and \"PV\" values are actual conditions in the simulation chambers.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac0e",
      "fullPath": "DAP Drobo/RodentResearch/RR05/EnvironmentalMonitoring/ISS_ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 5 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\n- Parameters: \nTemperature (degrees Celsius)\nRelative humidity (percentage)\nCarbon dioxide (parts per million)\n\"SP\" values are the set point from the ISS cabin near the rodent habitats and \"PV\" values are actual conditions in the simulation chambers.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac10",
      "fullPath": "DAP Drobo/RodentResearch/RR06/EnvironmentalMonitoring/ISS_ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 6 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\n-- ISS Cabin and Ground Simulation Chamber (ISSES)\nDate ranges - Chamber 2: December 10, 2018 - January 11, 2019; \nChamber 3: December 6, 2017 - February 6, 2018\nIncludes raw, tabular and graphed data (XLSX)\nChamber data are programmed from ISS cabin data. \nParameters: date and time (GMT), time (Eastern), temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million) values. Headers are: Log Date/Time GMT, Controller Time, Temp, % RH, and Aux, respectively. \"SP\" values are the set points and \"PV\" values are the actual values for the chamber. Oxygen data are not collected.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac11",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR07/EnvironmentalMonitoring/ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 7 ground control re-run mission data collection contains environmental monitoring data for the ground control operations that were reconducted at Northwestern University in Evanston, Illinois in 2021. For this re-run mission, only ground operations were conducted. The original mission occurred in 2018. For associated flight data, see the records for Rodent Research 07.\n-- ISS Cabin Ground Simulation Chamber (ISSES)\nDate range is March 21 - June 6, 2021 (DOY 80-157)\nData are provided for chambers 2 and 3.\nData are presented as raw data points and are graphed by parameter. \nParameters: Temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million).\nIn data headings, SP is the Set point and PV represents what actually happened in the chamber.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac12",
      "fullPath": "DAP Drobo/RodentResearch/RR07/EnvironmentalMonitoring/cabin_ISSES_ch2_RR7.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 7 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\nDate range: July 1, 2018 - September 18, 2018\nChamber data are programmed from ISS cabin data. \nParameters: date and time (GMT), time (Eastern), temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million). \"SP\" values are the set points and \"PV\" values are the actual values for the chamber.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac14",
      "fullPath": "DAP Drobo/RodentResearch/RR08/EnvironmentalMonitoring/cabin_ISSES_ch2_3_RR8.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 8 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\nDate range is December 1, 2018 - January 14, 2019\n- Parameters: \nTemperature (degrees Celsius)\nRelative humidity (percentage)\nCarbon dioxide (parts per million)\n\"SP\" values are the set point from the ISS cabin near the rodent habitats and \"PV\" values are actual conditions in the simulation chambers.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac16",
      "fullPath": "DAP Drobo/RodentResearch/RR09/EnvironmentalMonitoring/cabin_ISSES_ch3_RR09.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 9 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\nNote: Ground control operations were cut short due to a hurricane so were re-run from May 12 - June 18, 2018. \nDate range is 5/12/2018 - 6/18/2018\nChamber data are programmed from ISS cabin data. \nParameters: date and time (GMT), time (Eastern), temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million) values. Headers are: Log Date/Time GMT, Controller Time, Temp, % RH, and Aux, respectively. \"SP\" values are the set points and \"PV\" values are the actual values for the chamber. Oxygen data are not collected.\n\nBoth the cabin and chamber data are logged in five-minute intervals and the chamber values are graphed, with one graph each for temperature, relative humidity, and carbon dioxide.\nNote: The date range in the file represents the ground control re-run which occurred later because a hurricane cut the original ground control operations short. A crosswalk indicating flight dates was not included in this file. See the time table below. The duration of the ground control experiment for RR9 was longer because of the live animal return. The last three days of data in the original file acquired (June 16-18) are not from the cabin/ISSES chamber but from the SpaceX Dragon cabin. These three days of data were deleted from the cabin_ISSES_ch3_RR09.xlsx archived file. See the SpaceX file for those data.\nRR9 ground control re-run dates\n   5/12/18 Launch\n   5/15/18 Transfer\n   6/14/18 Undock\n   6/14/18 Splashdown\nRR9 flight dates\n   8/14/17 Launch\n   8/18/17 Transfer\n   9/17/17 Undock \n   9/16/17 splashdown\n\ncabin_ISSES_ch3_RR09.xlsx",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac17",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR010/EnvironmentalMonitoring/cabin_ISSES_ch3_RR10.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 10 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS) and associated ground operations at the Roskamp Institute in Sarasota, Florida. These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at the Roskamp Institute.\nThese data are from both the ISS cabin near the habitats and the ground control ISSES incubator chamber that simulates the cabin environment. The chamber data are programmed from ISS cabin data.\nDate range: \nCabin (GMT) December 4, 2020 - January 3, 2021 (DOY 339-003)\nChamber (EST) Dec. 6, 2020-January 6, 2021 (DOY 341-006)\nParameters:\nCarbon dioxide - parts per million\nTemperature - degrees Celsius\nRelative humidity - percentage \nISS Cabin time stamp (TelemetryGmtTime) - Greenwich Mean Time\nISSES Chamber time stamp (PlaybackLocalTime) - Eastern Standard Time\nData are logged in one-minute intervals and the chamber values are graphed, with one graph each for temperature, relative humidity, and carbon dioxide.\nExplanation of anomalies:\n1. The first 600 TelemetryGmtTime time stamps are logged as 2009 while corresponding PlaybackLocalTime values are logged as 2020. The 2009 values are 2020. 2009 was used as part of the procedure for to deconflict the two data streams. The month, day and time are correct.\n2. Several points read as \"SUCCESS\" instead of a valid value. These are log errors from the raw data recorded in 1-second intervals. The submitter considers these errors to be acceptable in the context of the set as a whole.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac1d",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR017/EnvironmentalMonitoring/ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 17 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\n   Date range:\n     Chamber 3: July 24 - September 6, 2019 (DOY 205 - 249)\n     Chamber 7: July 24 - August 27, 2019 (DOY 205 - 239)\nChamber data are programmed from ISS cabin data. \nParameters: date and time (GMT), time (Eastern), temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million). \"SP\" values are the set points and \"PV\" values are the actual values for the chamber. Oxygen data are not collected.\nNote: Data appear to end before the experiment ended.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac1f",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR019/EnvironmentalMonitoring/cabin_ISSES_ch2+3_RR19.xlsx",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 19 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at Kennedy Space Center (KSC). These datasets contain environmental data for the ISS cabin near the rodent habitats and the associated cabin Ground Simulation Chamber (ISSES) at KSC.\nDate range: \n   Chamber 2: December 3, 2019 - January 7, 2020 (2019 DOY 337 - 2020 DOY 007)\n   Chamber 3: December 3, 2019 - January 7, 2020 (2019 DOY 337 - 2020 DOY 007)\nChamber data are programmed from ISS cabin data. Parameters: temperature (degrees Celsius), relative humidity (percentage), and carbon dioxide (parts per million). \"SP\" values are the set points and \"PV\" values are the actual values for the chamber. Oxygen data are not collected. Raw data are recorded in one-minute intervals. Data are presented in both raw, tabular format and as graphs.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac21",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RR023/EnvironmentalMonitoring/ISSES",
      "subcategory": "ISS_ISSES",
      "subdirectory": "Env",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 23 mission data collection contains environmental monitoring data for the Rodent Research payload on the International Space Station (ISS), and in associated ground controls at the Roskamp Institute in Sarasota, Florida. This series includes data from both the ISS cabin near the habitats and the ground control ISSES incubator chamber that simulates the cabin environment. The chamber data are programmed from ISS cabin data. Data are presented in human-readable (XLSX) format.\nDate range: December 4, 2020 - January 10, 2021 (DOY 339 - 010)\nParameters:\nCarbon dioxide - parts per million\nTemperature - degrees Celsius\nRelative humidity - percentage \nISS Cabin time stamp (TelemetryGmtTime) - Greenwich Mean Time\nISSES Chamber time stamp (PlaybackLocalTime) - Eastern Standard Time \n\"SP\" values are the set points from the ISS cabin and \"Actual\" values are the actual values for the ISSES chamber. Both the cabin and chamber data are logged in one-minute intervals and the chamber values are graphed, with one graph each for temperature, relative humidity, and carbon dioxide. There are numerous gaps in the data from January 10-14.",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    },
    {
      "id": "6375b4f6313d542fb5edac22",
      "fullPath": "CLSR/alsda_master/Dap Drobo/RodentResearch/RRD1/EnvironmentalMonitoring/VehicleData_CarrierSpX23_RRD1_RESTRICTED",
      "subcategory": "SpaceX",
      "collectionSite": "",
      "fileSize": 0,
      "description": "This portion of the Rodent Research 22 Demonstration 1 Validation mission data collection contains vehicle cabin environment and acceleration data for the SpaceX CRS-23 Dragon spacecraft as it carried the Rodent Research payload to the International Space Station. This mission was flight operations only, no ground controls. A reference key showing parameters and units of measure is included. Data are split across three files.\nDate range: August 29, 2021 - October 1, 2021 (DOY 241-274)\nParameters include:\nCabin pressure (PSIA)\nPartial pressure of oxygen (PSIA)\nPartial pressure of carbon dioxide (MMHG)\nTemperature (degrees Celsius)\nRelative humidity (percentage)\nBody accelerations (m/s^2)",
      "collectionDays": "",
      "category": "6376601f664a6ddef2d9f8c9"
    }
  ],
  "versionInfo": { "documentKey": "9e5a5f702ffc479fbbb335e2a067e6ad", "version": 1, "deleted": false },
  "parents": {
    "mission": [
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-2" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-1" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-4" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-6" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-3" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-5" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-9" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-8" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-10" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-11" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-13" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-12" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-14" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-15" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-16" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-18" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/Eu:CROPIS" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-19" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-21" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-22" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-23" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-24" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-17" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-25" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-26" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-28" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX-27" },
      { "mission": "https://osdr.nasa.gov/geode-py/ws/api/mission/SpaceX%20Inspiration%204" }
    ]
  }
}
    
```

### API Requests with Python <a href="#python" id="python"></a>

### Basic API Request

For basic API requests, the requests python library can be used. Install the library with the command:

We can use the requests libray to make API calls to any of the endpoints above. The python code below shows the exact commands needed to read the API endpoints that return JSON. Replace API\_ENDPOINT\_HERE with any API endpoint that returns JSON, as in the example.

```
    import requests
    response = requests.get("API_ENDPOINT_HERE").json()
    # Example:
    response = requests.get("https://osdr.nasa.gov/osdr/data/osd/files/87").json()
  
```

### Resources <a href="#resources" id="resources"></a>

For more information on making API requests with python, visit [https://www.dataquest.io/blog/python-api-tutorial/](https://www.dataquest.io/blog/python-api-tutorial/).

For more information on the OSDR Public API, visit [https://api.nasa.gov/](https://api.nasa.gov/).

![NASA GeneLab – Open Science for Life in Spac](.gitbook/assets/GeneLab\_patch.png)

### Contacts
