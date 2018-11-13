# Statamic Accordion Group

Stash groups of fields from long fieldsets away in accordion-style toggle boxes.

## Installation

To install this fieldtype, download the addon files from the [Statamic marketplace](https://statamic.com/marketplace/addons/accordion-group) and place the `AccordionGroup` folder in your `site/addons` directory. You should then be able to add 'Accordion Group' fields to your fieldsets.

## Setting up fieldsets

You will need to define fieldsets for groups of fields that you wish to place within an accordion group, once a fieldset has been built you can tell you accordion group to use that fieldset, either through the field 'extras' interface or in your yaml.

## Example

In the example below we are storing fields from the 'metadata' fieldset in an accordion group:

```yaml
fields:
  metadata:
    type: accordion_group
    display: Metadata
    instructions: Optimize the metadata for this page or post.
    child_fieldset: metadata
```

![Example metadata field in CP](https://raw.githubusercontent.com/AndrewHaine/statamic-accordion-group/master/docs/img/statamic-accordion-group-cp-xmpl.gif)

## How do I use this in my templates?

In templates the fields contained within accordion groups will be prefixed with the name of the group, for example the `meta_title` field will become `metadata.meta_title`:

```html
{{ if metadata.page_no_index }}
<meta name="robots" content="noindex,nofollow" />
{{ /if }}
<title>{{ metadata.meta_title or title }}</title>
<meta name="description" content="{{ metadata.meta_description }}" />
```

## Nesting?
Yes, but not recommended when your child fieldset contains the parent accordion field.
