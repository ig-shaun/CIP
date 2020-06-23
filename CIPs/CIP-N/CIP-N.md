---
cip: 
title: Identity Routing Document (IRD)
author: Michael Sena (http://github.com/michaelsena), Joel Thorstensson (http://github.com/oed)
discussions-to: https://github.com/ceramicnetwork/CIP/issues/3
status: Pending
category: Standards
type: RFC
created: 2020-05-22
requires: -Add CIP for Tile-
replaces:
---

## Simple Summary

The Identity Routing Document (IRD) is a top-level routing table for a DID's resources.

## Abstract

A decentralized identifier (DID) is the minimum requirement for establishing a platform-agnostic digital identity. But digital identities are much more than just an identifier; they are the complete set of resources (such as metadata, keys, information, and capabilities) related to the DID. Currently there is no standardized way of associating this information to a DID which limits discovery, making true identity interoperability extremely difficult.

The Identity Routing Document (IRD) defines an extensible top-level routing table for a DID's resources. By standardizing how resources are associated to a DID, IRD simplifies cross-platform resource discovery and enables identity-centric interoperability across the web.

> IRD is a component of the [Identity Resource Routing Protocol (IRRP)](http://hi.com) and is commonly used in conjunction with the other IRRP documents.

## Motivation

Many modern developers aspire to build applications in a way that relies on a user-controlled model of identity and resources (data/services) for various reasons ranging from simplified onboarding to reduced liability. This model assumes that identities and data can be shared across applications and platforms. As a result, IRD aims to provide:

**Identity standardization:** Decentralized identifiers (DIDs) are the foundational requirement for interoperable, platform-agnostic identities. However, in practice "identity" is much more than just an identifier. Identity is the complete set of data, resources, and capabilities that are associated with a DID. Since DIDs only provide an identifier, they are alone insufficient. IRD provides a standardized and infinitely extensible way to associate these many resources to a DID. 

**Resource discoverability:** In a user-centric model of application development, when a user logs-in to a site that site needs to access the resources associated with that user's DID, wherever they may exist (servers, distributed networks, etc). This requires simple discovery and routing. IRD provides the top-level routing information to all of these resources.

**DID-agnostic support:** Given the number of DID providers only continues to increase, standardization around resource mappings is paramount; failing to do this will result in each DID method implementing their own system for resource routing which would limit the interoperability and utility of DIDs. IRD can support any DID.

## Specification

The IRD specification consists of a doctype, a schema, and a table.

### Doctype

IRD is a [tile doctype (CIP-N)](http://hi.com) whose content adheres to the schema below.

### **Schema**

The IRD schema defines a key-docId store which maintains a list of properties and values that must be Ceramic docIds.

```jsx
```json
{
  "$schema": "http://json-schema.org/draft-06/schema#",
  "$ref": "#/definitions/ird",
  "definitions": {
    "ird": {
      "type": "object",
      "additionalProperties": false,
      "properties": {
        "account-links": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "profile": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "sources": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "services": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "keychain": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "claims": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        },
        "connections": {
          "type": "string",
          "pattern": "^ceramic:\/\/.+"
        }
      },
      "title": "ird"
    }
  }
}
```

### Table

The [IRD table](http://hi.com) contains the standard set of properties that may be contained in any given IRD. New properties can be added to the IRD table by following the steps below. Additional properties not found in this table may be stored in any IRD, however they may be less interoperable since others may not know what they represent.

**How to add a new property to the IRD table**

1. Choose a unique, descriptive property name.
2. Add a description for your property.
3. Submit a PR to the CIP repository updating the IRD table with your property.
4. Mention the authors of this CIP in the comments of your PR.

## **Example**

An example IRD that includes standard profiles, accounts, keychains, services, sources, and connections properties.

```jsx
doctype: tile
schema: <insert canonical schema for IRD>
content:

```json
{
  "prd": "ceramic://bafyljsdf1",
  "ard": "ceramic://bafysdfoijwe2",
  "krd": "ceramic://bafysdfoijwe3",
  "serd": "ceramic://bafysdfoijwe4",
  "sord": "ceramic://bafysdfoijwe5",
  "crd": "ceramic://bafysdfoijwe7"
}
```

## Suggested Usage

**DIDs:** IRD can be used with any DID. A link to IRD should be stored in the DID document, ideally under an `ird` property to make it discoverable by simply resolving the DID document.

**Content:** It is recommended that IRD be used as a top-level router to store links to other Ceramic documents that function as category routers to subsets of resources. This keeps IRD minimal and provides a logical structure for information. The properties for profiles (PRD), accounts (ARD), keychains (KRD), etc found in the IRD table above are examples of documents that act as categorical routers.

## Rationale

**Extensibility & Flexibility:** It is impossible to predict all of the types of resources that need to be associated with any particular DID. Therefore IRP was designed to be infinitely extensible to support routing to any kind of resources.

**Decentralzation & Trust:** Identity routing information is mission-critical data that needs to be globally-available and censorship-resistant, and live permissionlessly in the public domain (not on any single server). Additionally this information should be owned by a DID and will need to be updated from time to time. These requirements make Ceramic the most appropriate platform for publishing identity routing content.

## Implementation

**IRD Schema:** The version of the IRD schema defined in this CIP can be found at [ceramic://bafy.../?version](http://hi.com).

**IRD Table:** The table containing standard IRD properties can be found [here](http://hi.com).

**Libraries:** Not yet available.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
