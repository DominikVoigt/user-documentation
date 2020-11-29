# Conducting automated cross-library search

## Providing a study file for automated search

To provide automated search JabRef needs the set of targeted digital libraries and the used queries.
To provide these a `study.yml` file, also called study definition, has to be created.
This file contains different entries with different information.
This file have to be provided within an otherwise empty fully setup git repository.

Example study definition file:

```yaml
authors:
  - Jab Ref
title: TestStudyName
last-search-date: 2020-11-26
research-questions:
  - Question1
  - Question2
queries:
  - query: Quantum
  - query: Cloud Computing
  - query: '"Software Engineering"'
databases:
  - name: Springer
  - name: ArXiv
  - name: IEEEXplore
    enabled: false
}
```

## Executing the automated search

To execute the automated search navigate in the toolbar to **Tools\|Start systematic literature review** and click it.

![Start an automated search](../../.gitbook/assets/start-SLR.png)

Then select the `study.bib` file in the file explorer dialogue that is located in the git repository.

![Select the study definition file](../../.gitbook/assets/select-study-definition.png)

After that the automated search is executed and any new studies are commited and pushed to the configured git repository.
The local repository now contains the retrieved studies sorted by the respective query and digital library that retrieved it.

![Repository structure](../../.gitbook/assets/repository-structure.png)

The `result.bib` located in the query folder contains the merged results from all fetcher for the respective query.
The `studyResult.bib` contains the merged results for all queries.
