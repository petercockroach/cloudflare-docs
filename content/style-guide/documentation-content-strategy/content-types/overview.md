---
pcx_content_type: concept
title: Overview

---

# Overview

## Purpose

The purpose of a landing page is to welcome users and provide an overview of the product.

## Tone

Accessible, welcoming, conversational, outspoken

## content_type

`overview`

## Structure

### Required components

**Metadata title**: Overview

**Title**: Name of the product, group of products, or conceptual content area. H1. Usually a noun. Do not add "documentation" to the title. Do not use gerund phrases.

**Intro/overview**: Brief welcoming introductory content. May be combined with product description.

**Product description**: What does this product do? Why would you use it?

**Product availability**: What plan(s) is this available to? Review [available plan types](https://github.com/cloudflare/cloudflare-docs/blob/production/layouts/shortcodes/plan.html#L1).

**Product attributes**: What is included with this product? (Specific actions, protections, etc.)

### Optional components

**Features**: A few main features specific to product. Includes a link to relevant documentation on feature.

**Related products**: Links to documentation for products used or configured together with current product.

**More resources**: External links to related resources, such as plans, pricing. Do not duplicate the information from the footer. Also, if the product is free to use or there are not any useful links, feel free to skip this section. Review [available icons in the source code](https://github.com/cloudflare/cloudflare-docs/tree/production/static/icons/resources).

**Visual**: Graphic or image that enhances the landing page. It should be something relatively static that will not require much (if any) updating in the future.

**Integration information**

## Template

```

---
title: Overview
weight: xx
layout: overview
pcx_content_type: overview
---
 
# Cloudflare <product name> (or {{</*beta*/>}}Cloudflare <product name>{{</*/beta*/>}} for products in beta)
 
{{</*description*/>}}
Product description - What does this product do? Why would you use it? Short overview of product capability (~10-15 words).
{{</*/description*/>}}
 
{{</*plan type="<type>"*/>}}
 
Summary - Brief welcoming introductory content. A few sentences describing the product’s benefits to the customer. Focus on customer benefit but can also include general product information.
 
---
 
## Features
 
{{</*feature header="Name of feature" href="/link/to/feature/"*/>}}
Description highlighting capabilities of product feature. This section accepts Markdown lists for multiple attributes.
{{</*/feature*/>}}
 
---
 
## Related products
 
{{</*related header="<Name of product>" href="</link/to/product>" product="<slugified-product-name>"*/>}}
Description of product used together or connected configuration with current product.
{{</*/related*/>}}
 
---
 
## More resources
 
{{</*resource-group*/>}}
 
{{</*resource header="<Resource name>" href="https://www.cloudflare.com/link-to-resource/" icon="icon-name"*/>}}
Description of external resource related to current product.
{{</*/resource*/>}}
 
{{</*/resource-group*/>}}

```

## Additional Information

Only use Overview for the first page in a developer documentation set.

## Examples

[Argo Smart Routing documentation](/argo-smart-routing/)

### Many availabilities

[Images](/images/) is an example of a product whose availability is complex, and is not easy to just use one type of plan. To create components for each plan type, insert `{{</*plan type="<PLAN_TYPE>"*/>}}` below each of the feature component, like so:

```
{{</*feature header="<CLOUDFLARE_PRODUCT>" href="/path/to/product"*/>}}

{{</*plan type="PLAN_TYPE"*/>}}

Description of content in this section.

{{</*/feature*/>}}
```