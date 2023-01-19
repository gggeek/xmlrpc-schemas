XML-RPC Schemas
===============

A collection of _completely unofficial_ Interface Definition Language schemas for XML-RPC.

## Introduction

This project is an exploration in the possibility of using existing schema languages to define XML-RPC webservices, with
the end goal of both supporting existing toolchains and allowing the development of new ones which allow practices
such as automated code-generation and API verification.

A brief description of the supported / tested IDL languages follows.

### WSDL

Might be useful in defining some WSDL file describing xmlrpc services.
The XSD is not quite accurate, due to limitations in the definition language.
RELAX NG should be 100% precise and accurate - but there seems to be scarcity of tools supporting usage of it in a WSDL.

Other known implementations:

- https://learn.microsoft.com/en-us/openspecs/sharepoint_protocols/ms-metaweb/1c3a29ca-dc34-441c-840e-cb86a72460e9


[![License](https://poser.pugx.org/phpxmlrpc/schemas/license)](https://packagist.org/packages/phpxmlrpc/schemas)
[![Total Downloads](https://poser.pugx.org/phpxmlrpc/schemas/downloads)](https://packagist.org/packages/phpxmlrpc/schemas)
