XML-RPC Schemas
===============

A collection of _completely unofficial_ Interface Definition Language schemas for XML-RPC.

## Introduction

This project is an exploration in the possibility of using existing schema languages to define XML-RPC webservices, with
the end goal of both supporting existing toolchains and allowing the development of new ones which allow practices
such as automated code-generation and API verification.

A brief description of the supported / tested IDL languages follows.

## WSDL

Might be useful in defining some WSDL file describing xmlrpc services.
The XSD is not quite accurate, due to limitations in the definition language.
RELAX NG should be 100% precise and accurate - but there seems to be scarcity of tools supporting usage of it in a WSDL.

Other known implementations:

- https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-metaweb/1c3a29ca-dc34-441c-840e-cb86a72460e9

### Details

The XML-RPC protocol has been specified a long time ago, at the dawn of XML, and is described only in natural language.
Attempts have been made to "reverse specify" it with DTD or XSD, with little success.
Both definition languages are in fact too limited in their capability of expressing valid xml constructs to capture in a
complete and correct fashion the XML-RPC semantics (see http://www.cafeconleche.org/books/xmljava/chapters/ch02s05.html
for more details. Suffice to say that XSD does not allow to specify two consecutive xml elements with the same name but
of different types, such as the faultCode and faultReason response members happen to be).</para>

The RELAX-NG definition language on the other hand has been found capable enough to fully describe XMLRPC, and the
schema that is part of this distribution can be used to validate any XMLRPC request or response conforming to the spec.
IT IS NOT AUTHORITATIVE because the XML-RPC specification is copyright by Dave Winer, and he seems to have lost
interest in any further development of the protocol, but it should be considered accurate and production ready (if you
find any bugs, please let the authors know).

This situation is very unfortunate, since WSDL has emerged as a widely accepted web services standard, and a plethora of
tools exist to parse existing WSDL files and automatically generate code stubs or generate WSDL definitions from existing
code. If a WSDL representation of XMLRPC webservices could be generated, the net result would be greatly increased
interoperability between SOAP clients and toolkits and XMLRPC server implementations.

Even though the apparent goal of the WSDL language design was to allow description of every possible message exchange,
using every conceivable xml serialization over any transport (and a lot of the redundancy, verbosity and complication of
the language are direct consequence of the flexibility sought), existing implementations de-facto only support the SOAP
binding for webservices, and XSD as language definition schema. RELAX-NG, while nominally accepted, has yet to find
widespread usage in webservices toolkits. This leaves us with almost-but-not-quite interoperable solutions.

### File list

- schema.rnc: the same RELAX NG schema definition as found in schema.rng, using ... notation
- schema.rng: a RELAX NG schema definition describing XMLRPC (using xml notation)
- xmlrpc.wsdl: a XML Schema Definition attempting to describe XMLRPC method calls and responses
- xmlrpc.xsd: a XML Schema Definition attempting to describe XMLRPC

## Other IDLs

### XRDL

Originally hosted at https://code.google.com/archive/p/xrdl/, the project seems to have been dormant for some time.
There are forks on GitHub, such as https://github.com/mumitr0ll/xrdl, which also seem not very actively maintained.

### system.describeMethods

The specification is available at https://xmlrpc-epi.sourceforge.net/specs/rfc.system.describeMethods.php.
To the best of my knowledge, it was never implemented outside the xmlrpc-epi C library.

## Other resources

### Converting XML-RPC to SOAP

An XSLT file is available at http://web.archive.org/web/20010611155715/http://soap.develop.com/xmlrpc/fromxr.xsl

A guide on how to achieve interoperability with SOAP (letting SOAP clients send requests to XML-RPC servers) can
be found at https://www.xml.com/pub/a/ws/2002/12/18/endpoints.html

[![License](https://poser.pugx.org/phpxmlrpc/schemas/license)](https://packagist.org/packages/phpxmlrpc/schemas)
[![Total Downloads](https://poser.pugx.org/phpxmlrpc/schemas/downloads)](https://packagist.org/packages/phpxmlrpc/schemas)
