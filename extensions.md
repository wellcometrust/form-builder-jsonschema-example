# Proposed extensions to JSON Schema

Below are the keywords, values and other elements the example schema uses to extend Draft-07 of JSON Schema. 

## Custom keywords 

- x-shouldAutoComplete: Boolean (default: null) 

This describes whether a field can be auto-completed on the front-end. Helpful for preventing auto-complete on potentially privacy-sensitive fields.  

- x-salesforceMapping: String (default: “”) 

This will be used to provide the middleware with the context of where the value of a form field exists in Salesforce. This could be an ID or table reference. 

- x-renderer: String, oneOf['password', 'rte', 'textarea', 'typeahead']` (default: null) 

This property is useful for describing what kind of component should render a form field, when the value does not exist natively in JSON Schema. 

- enumNames: Array (default: null)  

When an enum is used, this provides labels for each of the values in the enum. Taken from https: //react-jsonschema-form.readthedocs.io/en/latest/usage/single/#custom-labels-for-enum-fields 

## Custom values: 

- Format: “data-url” 

Denotes a file upload field. See https: //react-jsonschema-form.readthedocs.io/en/latest/usage/widgets/#string-formats 

## Custom approach to dependencies: 

- Adopt a restricted use of "oneOf" keyword, see https://react-jsonschema-form.readthedocs.io/en/latest/usage/dependencies/#dynamic which explains this approach 

## Needs discovery 

The following points are areas which are included in the example schema, but need discovery in to how to achieve.

### x-formula 

We desire a property for declaring that a field should use calculations based on the values of other fields. 

### HTML in descriptions 

It’s not clear from the JSON Schema specs whether it is valid to use HTML inside the “description” value. If it is not, we will need to allow for this somehow. 

### Dependencies 

This is probably the most complex piece of customisation we are proposing to the schema, so it would be good to discuss the approach we’ve proposed (above) in the example schema to get a range of opinions. 