# Glossary
A list of terms and what they mean in Meteor context. This document is intended for contributors. 

If you are reading Meteor code or Meteor docs anywhere and you find that a term is not clear enough or Meteor has used the term in a way that is not easy to understand please submit a PR adding a new term to this glossary. You don't need to be afraid of being wrong, we will review the PR and we can define the term in the best way possible in the review process.

## Core package
A core package is of course a Meteor package. They are maintained in the official Meteor repo.

Core packages don't have .versions file as they are always released from a checkout of Meteor.

Every package that lives exactly in the folder `packages/` in the Meteor repository is considered a core package. If the packages lives in sub-folders of `packages`, like `deprecated` or `non-core` they are not considered a core package.

## Isobuild
Meteor has a packaging system called "Isobuild". Isobuild knows how to compile the same JavaScript code-base to different architectures: browser, node.js-like server environment (could be Rhino or other) or a webview in a Cordova mobile app.

related terms: [Isopack](#isopack), [Unibuild](#unibuild)

## Isomorphic
Having similar structure or appearance but being of different ancestry. Broken down, “iso-” means equal, and “-morphic” means having the same shape, form, or structure.

Isomorphism is not specific to Meteor, but rather it is a core quality of the Meteor environment where different platforms and resources are united in a similar interface for application-programmers.

related terms: [Isomorphic JavaScript](#isomorphic-javascript), [Isobuild](#isobuild), [Isopack](#isopack), [Isopackets](#isopackets)

## Isomorphic JavaScript
JavaScript code that can run on both the server and client. Also called “Universal JavaScript.”

An obstacle to writing isomorphic JavaScript is that the server and client environments each have unique features to extend the programmer’s control and abilities. For instance, server-side JavaScript will include access to databases, other servers, the file system, etc., but the client-side environment might not have the same API for these features or even have these features at all.

Meteor bridges this gap between server and client JavaScript with abstractions that allow application-programmers to write the same code in either context with isomorphic Javascript.

related terms: [Isomorphic](#isomorphic)

## Isopack
Each package used by Isobuild forms an Isopack. Isopack is a package format containing source code for each architecture it can be ran on. Each separate part built for a separate architecture is called "Unibuild".

related terms: [Isobuild](#isobuild), [Unibuild](#unibuild)

## Isopackets
Isopacket is a set of isopacks. Isopackets are used only inside meteor-tool.

An isopacket is a predefined set of isopackages which the meteor command-line tool can load into its process. This is how we use the DDP client and many other packages inside the tool. The isopackets are listed a constant called ISOPACKETS.

related terms: [Isopack](#isopack), [meteor-tool](#meteor-tool)

## meteor-tool
This is the Meteor command-line tool. Most of the code for it is in the [tools directory](https://github.com/meteor/meteor/tree/devel/tools) of the Meteor repository.

The Meteor tool also includes testing functionality and example apps for the Meteor framework.

It also defines the version of Meteor, when we say that you are using Meteor 1.12.1 that means you are using meteor-tool@1.12.1. 

## Minimongo
A client-side implementation of the MongoDB API, against an in-memory JavaScript database. Minimongo is like a MongoDB emulator that runs inside a web browser. This allows application-programmers to store and retrieve data on the client with the same code as they would write on the server. The Minimongo API is a subset of the complete MongoDB node driver API.

In Meteor, Minimongo is primarily used as a sophisticated data cache for documents published by the server, but it is not limited to that. Minimongo is a [core package](#core-package) of Meteor.

related terms: [Isomorphic JavaScript](#isomorphic-javascript)

see more: [source code](https://github.com/meteor/meteor/tree/devel/packages/minimongo)

## Unibuild
Isopack is a package format containing source code for each architecture it can be ran on. Each separate part built for a separate architecture is called "Unibuild".

There are multiple reasons why we can't call it just "build" and historically the name "Unibuild" has been associated with parts of Isopacks. We also can't call it "Isobuild" because this is the brand-name of the whole build/packaging system.

related terms: [Isobuild](#isobuild), [Isopack](#isopack)
