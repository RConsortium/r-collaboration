# Registry of Open Data

A repository of publicly available datasets that are available for access from a wide variety of resources. Note that 
datasets in this registry are available via many different resources, but they are not provided by the R Consortium; 
these datasets are owned and maintained by a variety government organizations, researchers, businesses, and individuals.

## What is this for?

When data is shared on in this repository, it is the intent that anyone can analyze it and build services on top of it using a broad range of compute and 
data analytics products. Sharing data in the cloud lets data users spend more time on data analysis rather than data acquisition. 
This repository exists to help people promote and discover datasets that are available for analysis using R.

## How are datasets added to the registry?

Each dataset in this repository is described with metadata saved in a YAML file in the [/datasets](/datasets) directory. We use these YAML files to provide three services:

- A Registry of Open Data 
- A hosted YAML file listing all of the dataset entries
- Hosted YAML files for each dataset

The YAML files use this structure:

```yaml
Name:
Description:
Documentation:
Contact:
ManagedBy:
UpdateFrequency:
Tags:
  -
License:
Resources:
  - Description:
    ARN:
    Region:
    Type:
DataAtWork:
  Tutorials:
    - Title:
      URL:
      AuthorName:
      AuthorURL:
  Tools & Applications:
    - Title:
      URL:
      AuthorName:
      AuthorURL:
  Publications:
    - Title:
      URL:
      AuthorName:
      AuthorURL:
```

The metadata required for each dataset entry is as follows:

| Field | Type | Description |
| --- | --- | --- |
| **Name** | String | The public facing name of the dataset |
|**Description**|String|A high-level description of the dataset|
|**Documentation**|URL|A link to documentation of the dataset|
|**Contact**|String|May be an email address, a link to contact form, a link to GitHub issues page, or any other instructions to contact the producer of the dataset|
|**ManagedBy**|String|The name of the organization who is responsible for the data ingest process|
|**UpdateFrequency**|String|An explanation of how frequently the dataset is updated|
|**Tags**|List of strings|Tags that topically describe the dataset. A list of supported tags is maintained in the [tags.yaml](tags.yaml) file in this repo. If you want to recommend a tag that is not included in [tags.yaml](tags.yaml), please submit a pull request to add it to that file.|
|**License**|String|An explanation of the dataset license and/or a URL to more information about data terms of use of the dataset|
|**Resources**|List of lists|A list of AWS resources that users can use to consume the data. Each resource entry requires the metadata below:|
|**Resources > Description**|String|A technical description of the data available within the AWS resource, including information about file formats and scope.|
|**Resources > ARN**|String|Amazon Resource Name for resource, e.g. arn:aws:s3:::commoncrawl|
|**Resources > Region**|String|AWS region unique identifier, e.g. us-east-1|
|**Resources > Type**|String|Can be _CloudFront Distribution_, _DB Snapshot_, _S3 Bucket_, or _SNS Topic_. A list of supported resources is maintained in the [resources.yaml](resources.yaml) file in this repo. If you want to recommend a resource that is not included in [resources.yaml](resources.yaml), please submit a pull request to add it to that file.|
|**Resources > RequesterPays** (Optional)|Boolean|Only appropriate for Amazon S3 buckets, indicates whether the bucket has [Requester Pays](https://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html) enabled or not.|
|**DataAtWork  [> Tutorials, Tools & Applications, Publications]**  (Optional)|List of lists|A list of links to example tutorials, tools & applications, publications that use the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > Title**|String|The title of the tutorial, tool, application, or publication that uses the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > URL**|URL|A link to the tutorial, tool, application, or publication that uses the data.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > AuthorName**|String|Name of person or entity that created  the tutorial, tool, application, or publication.|
|**DataAtWork [> Tutorials, Tools & Applications, Publications] > AuthorURL**|String|(Optional) URL for person or entity that created the tutorial, tool, application, or publication.|
