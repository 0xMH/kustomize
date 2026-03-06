---
title: "ReplacementTransformer"
linkTitle: "ReplacementTransformer"
weight: 6
date: 2026-03-06
description: >
  ReplacementTransformer copies values from a source field into any number of target fields.
---

See [Transformers]({{< relref "../Transformers" >}}) for common required fields.

* **apiVersion**: builtin
* **kind**: ReplacementTransformer
* **metadata** ([ObjectMeta](https://kubernetes.io/docs/reference/kubernetes-api/common-definitions/object-meta/#ObjectMeta))

  Standard object's metadata.

* **replacements** (\[\]Replacement)

  A list of replacements, where each entry copies a value from a source into one or more targets.
  Each entry must use either inline source/targets fields or a path to an external file, but not both.

  _Each Replacement has the following fields:_

  - `source`: The source of the value. Selects a single resource by group, version, kind, name, and namespace. The `fieldPath` subfield specifies which field to read from (defaults to `metadata.name`). An `options` subfield supports `delimiter` and `index` for partial string extraction.
  - `targets`: The fields to write the value to. Each target uses `select` to match resources by group, version, kind, name, namespace, annotationSelector, or labelSelector. A `reject` field can exclude resources from the selected set. The `fieldPaths` subfield specifies which fields to write to (defaults to `metadata.name`). An `options` subfield supports `delimiter`, `index`, and `create` for partial string replacement and field creation.
  - `path`: Path to a file containing one or more replacement definitions. Cannot be combined with inline source/targets.

  See the [replacements]({{< relref "../Kustomization%20File/replacements.md" >}}) kustomization field for the full schema, field path syntax, and examples.
