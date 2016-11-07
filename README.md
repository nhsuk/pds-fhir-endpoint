# NHS Spine Test Harness

Docker orcherstration to get the PDS Care Integration Pattern POC up and running and talking to TKW.

This repo is just a compose and configuration wrapper for the following

[https://github.com/nhs-ciao/ciao-pds-fhir](https://github.com/nhs-ciao/ciao-pds-fhir)


## Dependencies
Images on dockerhub that are used:

* hscic/tkw-spine
* hscic/ciao-pds-fhir

Build steps for the above images was found here:

[http://developer.nhs.uk/community/blogs/experiments-with-containers/](http://developer.nhs.uk/community/blogs/experiments-with-containers/)

## Usage

`docker-compose up -d`

`curl "http://localhost:8080/fhir/Patient?family=LEWINGTON"`

returns a single FHIR patient resource which acts as a facade to the PDS TKW
