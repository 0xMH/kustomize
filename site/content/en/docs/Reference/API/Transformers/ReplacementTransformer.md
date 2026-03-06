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

  See the [replacements]({{< relref "../Kustomization%20File/replacements.md" >}}) kustomization field for the full schema, field descriptions, and examples.
