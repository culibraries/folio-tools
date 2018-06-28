# lint-raml -- Various processing tools to assist RAML and schema maintenance

Copyright (C) 2016-2018 The Open Library Foundation

This software is distributed under the terms of the Apache License,
Version 2.0. See the file "[LICENSE](LICENSE)" for more information.

# Introduction

These scripts investigate RAML and schema files.

Note that not all tools detect all potential issues.

The tools also compare examples with their RAML and schema.

Note that most projects have a standard directory layout (i.e.
`./ramls` holding the RAML files and Schemas, with a shared git submodule at `./ramls/raml-util`).
Some projects have known variations. The scripts are configured for that,
but options are provided to handle different situations. See the script help.

There is some assistance at [dev.folio.org/guides/raml-cop](https://dev.folio.org/guides/raml-cop)

# Tools

## lint-raml-cop.sh

Shell script to discover RAML files in a project and run 'raml-cop'.

Validates the RAML, ensures the $ref links in JSON Schema, and processes the examples.

Does not assess the schema name declaration key names in the RAML file.

### Prerequisites

- bash3+
- npm
- [raml-cop](https://github.com/thebinarypenguin/raml-cop)

### Method

Occasionally update raml-cop:

```shell
cd folio-tools/lint-raml 
npm install
```

Assuming folio-tools is cloned parallel to mod-notes:

```shell
cd mod-notes
../folio-tools/lint-raml/lint-raml-cop.sh mod-notes
```

Assuming folio-tools is cloned elsewhere, then specify the base directory,
i.e. the parent of FOLIO back-end cloned projects.

```shell
$GIT_1/folio-tools/lint-raml/lint-raml-cop.sh -b $GH_FOLIO mod-notes
```
