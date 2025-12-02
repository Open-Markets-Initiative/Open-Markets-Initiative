# Patents

A series of patents and open source projects have been created in the technical field of Binary Protocol Source Generation.

## Compiling protocol analysis code using protocol database

2002-06-24 to 2022-09-07

https://patents.google.com/patent/US7401326B1/en

A one-to-many approach using a database of symbols and a source generation tool for several languages.

## Systems and methods for data coding, transmission, storage and decoding

2005-11-14 to 2030-05-27

https://patents.google.com/patent/US8321465B2/en

A one-to-many approach using an interface design language via XML and a source generation tool for binary messages and storage.

This patent discloses market data source generation supporting binary messages, repeating groups, optional fields and some support for custom fields.  This is a message based system, lacking support for arbitrary headers and binary data.  Some language in the patent implies that plain text can be used to generate on binary messages.

## Universal Binary Specification

2022-10-13 to 2042-10-13

https://patents.google.com/patent/US12101388B2/en

A many-to-one approach that can normalize any binary interface description language or binary protocol documentation. 

## Binary Data Model Compiler

2024-09-24

https://patents.google.com/patent/US20240419416A1/en

A multistage, many-to-many, binary data model compiler using generic independent intermediate representations for binary data modeling. 

# Public Domain

## Abstract Syntax Notation

https://en.wikipedia.org/wiki/ASN.1 (1984)

Abstract Syntax Notation One (ASN.1) is an interface description language (IDL) for defining data structures that can be serialized and deserialized in a cross-platform way.

While ASN.1 is an attempt at generalizing data description via IDLs, a subset of encodings can encode a subset of binary data structures.

## Simple Binary Encoding

https://github.com/real-logic/simple-binary-encoding (2013)

Simple Binary Encoding (SBE) is an OSI layer 6 presentation for encoding and decoding binary application messages for low-latency financial applications.

SBE is a one-to-many approach using an Interface Design Language in XML and a source generation tool for several languages for message based binary protocols.

SBE includes support for binary messages, repeating groups and some support for field customization, similar to the architecture disclosed in US8321465B2.

## Kaitai Struct

https://kaitai.io (2015)

Kaitai Struct is a domain-specific language (DSL) that is designed with one particular task in mind: dealing with arbitrary binary formats.

A one-to-many approach using an Interface Design Language (.ksy) and a source generation tool for several languages for arbitrary binary protocols.

Due to differences in the IDL and scope of source generation cases, The Open Markets Initiative believes that Kaitai Struct does not infringe on any existing patents.  However, Kaitai struct cannot handle every case and does not provide the extensibility of a generic independent intermediate representation. 

# Notes

Binary protocols are fundamentally different from self-describing data formats like XML, JSON and FIX and form their own technical field.

According to the internet, Bloomberg would have had 6 years to file for patent infringement for SBE.

There are many existing implementations for generating binary protocols into several programming languages. For instance, patent US7401326B1 describes a one-to-many source generation method.  The Open Markets Initiative believes that the backend "plugin" architecture is within the public domain.

Existing source generation tools based on any singular IDL limits the scalability of a binary protocol source generation platform.

