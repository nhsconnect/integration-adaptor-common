## ARCHIVED - 2020-06-02

This repository is no longer maintained.
The code has been merged into the [NHSDigital/integration-adaptor-mhs] repo in the /common folder.

[NHSDigital/integration-adaptor-mhs]: https://github.com/NHSDigital/integration-adaptor-mhs

# NHS Integration Adaptors Common Utilities

This package contains common utilities used by the various projects that make up the NHS integration adaptors.

## CI Status
![](https://github.com/nhsconnect/integration-adaptor-common/workflows/Python%20package/badge.svg)

## Installation
To use this package as part of your project, ensure you have `pipenv` installed and on your path, then from your
project's directory run:
```
pipenv install git+ssh://git@github.com/nhsconnect/integration-adaptor-common.git@0.0.1#egg=integration-adaptors-common
```
This must be ssh and not https in order to be able to push your branches changes when this is an external repository. 

### Run Tests
From the integration-adaptor-common folder
- `pipenv run unittests` will run all unit tests.

### Coverage
From the integration-adaptor-common folder
- `pipenv run unittests-cov` will run all unit tests, generating a [Coverage](https://coverage.readthedocs.io/) report
in the `test-reports` directory.
- `pipenv run coverage-report` will print the coverage report generated by `unittests-cov`
- `pipenv run coverage-report-xml` will produce an XML version of the coverage report generated by `unittests-cov`, in a
[Cobertura](http://cobertura.github.io/cobertura/) compatible format
- `pipenv run coverage-report-html` will produce an HTML version of the coverage report generated by `unittests-cov`

### Analysis
To use sonarqube analysis you will need to have installed `sonar-scanner`. \
Ensure sonar-scanner is on your path, and configured for the sonarqube host with appropriate token. \
`sonar-scanner` will use `sonar-project.properties` to submit source to sonarqube for analysis.
 (See: [SonarQube](https://gpitbjss.atlassian.net/wiki/x/XQFfXQ))\
NOTE: Coverage will not show in the analysis unless you have already generated the xml report (as per above.)

## Working with both packages in Intellij

It is possible to edit the external package when using it in another repository, like nhais or mhs, in the same IntelliJ window as the opened project. There is no need to keep two windows open.

To do this you must ensure ssh was used to install this repository as an external package in your current repository to be able to push changes. 

Edit files: Open IntelliJ → selected repo → Pipenv → external libraries → integration-adaptor-common → Select file you want to edit → pop-up window select (I want to edit all files in this directory)

Create directory: cd to root of desired directory, `mkdir directory_name`

Create File: cd to root of desired directory, `touch file_name`

Add files: cd into directory of file created, git add (file-name)
 
Push changes: Location of virtualenv → src → integration-adaptor-common → git status → git diff → git commit → git push HEAD
