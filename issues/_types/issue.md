---
kind: mdbase.type
name: issue
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
      Priority: {type: string, enum: [low, medium, high, urgent]}
      Owner: {type: string}
      Doer: {type: string}
      Deadline:
        oneOf:
          - {type: string, format: date}
          - {type: string, format: date-time}
      Milestone: {type: string}
      BlockedBy: {type: array, items: {type: string}}
      Tag: {type: array, items: {type: string}}
collection:
  unique:
    - field: Identifier
  read_defaults:
    Status: open
---
