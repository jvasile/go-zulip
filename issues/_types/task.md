---
kind: mdbase.type
name: task
version: 1
schema:
  dialect: json-schema-2020-12
  value:
    type: object
    additionalProperties: false
    properties:
      type: {type: string}
      Identifier: {type: string}
      Title: {type: string}
      Description: {type: string}
      Status: {type: string, enum: [open, closed, pending, in-progress, reopened, duplicate, wontfix]}
      Owner: {type: string}
      Doer: {type: string}
      DeliverTo: {type: string}
      StartDate:
        oneOf:
          - {type: string, format: date}
          - {type: string, format: date-time}
      Deadline:
        oneOf:
          - {type: string, format: date}
          - {type: string, format: date-time}
      Client: {type: string}
      ContractPath: {type: string}
      Tag: {type: array, items: {type: string}}
collection:
  unique:
    - field: Identifier
---
