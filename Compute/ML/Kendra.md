**Amazon** **Kendra** is an intelligent search service powered by machine learning (ML).

[https://docs.aws.amazon.com/kendra/latest/dg/hiw-data-source.html](https://docs.aws.amazon.com/kendra/latest/dg/hiw-data-source.html)

[https://docs.aws.amazon.com/kendra/latest/dg/index-document-types.html](https://docs.aws.amazon.com/kendra/latest/dg/index-document-types.html)

- Designed to mimic interacting with a human expert
- Supports wide range of question types
- Factoid - Who, What, Where
- Descriptive - How do I do x?
- Keyword - What time is the keynote address (address can have multiple meanings) - Kendra helps determine intent

- Index - searchable data organized in an efficient way
- Data Source - where your data lives, Kendra connects and index from this location
	- S3, Confluence, Google Workspace, RDS, OneDrive, Salesforce, Kendra Web Crawler, Workdocs, FSX
- Synchronize with index based on a schedule
- Documents - Structured (FAQs), Unstructured (HTML, PDFS, text)