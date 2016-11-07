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

```javascript
{
  "resourceType": "Patient",
  "identifier": [
    {
      "label": "NHS Number",
      "system": "http://nhs.uk/fhir/nhsnumber",
      "value": "9449310394"
    }
  ],
  "name": [
    {
      "text": "MR [TRACE, ] LEWINGTON",
      "family": [
        "LEWINGTON"
      ],
      "given": [
        "TRACE",
        null
      ],
      "prefix": [
        "MR"
      ]
    }
  ],
  "telecom": [
    {
      "system": "phone",
      "value": "01132974444",
      "use": "home"
    },
    {
      "system": "phone",
      "value": "01234567444",
      "use": "home"
    },
    {
      "system": "phone",
      "value": "01234567899",
      "use": "home"
    }
  ],
  "gender": {
    "coding": [
      {
        "system": "http://hl7.org/fhir/vs/administrative-gender",
        "code": "M"
      }
    ],
    "text": "Male"
  },
  "birthDate": "1908-04-03T00:00:00-00:00",
  "deceasedBoolean": false,
  "address": [
    {
      "use": "home",
      "line": [
        null,
        "1 NETHERNE LANE",
        null,
        "COULSDON",
        null
      ],
      "zip": "CR5 1NR"
    }
  ]
}
```

returns a single FHIR patient resource which acts as a facade to the PDS TKW
