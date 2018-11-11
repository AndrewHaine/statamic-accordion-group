# Statamic Accordion Group

Stash groups of fields from long fieldsets away in accordion-style toggle boxes. This field is designed to work similarly to the existing [revealer fieldtype](https://docs.statamic.com/fieldtypes/revealer) except with a more intuitive toggleable interface.

## Installation

To install this fieldtype, download the addon files from the Statamic marketplace and put them in your `site/addons` directory. You should then be able to add 'Accordion Group' fields to your fieldsets.

## Setting up fieldsets

You will need to define fieldsets for groups of fields that you wish to place within an accordion group, once a fieldset has been built you can tell you accordion group to use that fieldset, either through the field 'extras' interface or in your yaml.

In the example below we are storing fields from the 'meta_data' fieldset within an accordion group:

```yaml
page_metadata:
  type: accordion_group
  display: Meta Data
  child_fieldset: meta_data
```
