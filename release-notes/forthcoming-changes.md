---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

**Table of contents**

   * [Simplification of UniParc XML root tag](#simplification-of-uniparc-xml-root-tag) - **From November 4, 2026**
   
# Simplification of UniParc XML root tag

We are going to simplify the root tag of the UniParc XML format by removing all attributes except the namespace:

```xml
<uniparc xmlns="http://uniprot.org/uniparc">
```

**Why:** Modern high-performance data processing frameworks (such as Apache Spark 4 and Databricks) utilize strict streaming XML APIs (like StAX / XMLStreamWriter). Characters like ``xmlns:xsi`` fail token validation, causing these engines to crash. Simplifying the root tag to the namespace element eliminates these character validation failures and ensures seamless integration with modern, large-scale streaming data pipelines.


**Impact:** Any code that parses the root tag and expects attributes other than the namespace must be updated to not rely on them.
