---
kind: mdbase.type
name: gitlab-issue
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
      Status: {type: string}
      Priority: {type: string}
      Milestone: {type: string}
      BlockedBy: {type: array, items: {type: string}}
      Tag: {type: array, items: {type: string}}
      Repository: {type: string}
      RemoteID: {type: string}
      RemoteNumber: {type: string}
      RemoteURL: {type: string, format: uri}
      SyncTime: {type: string, format: date-time}
---
