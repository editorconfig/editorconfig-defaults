EditorConfig Defaults
=====================

Description of the file format
------------------------------

```json
{
  "file_format": "1.0",
  "version":"0.1.0",
  "matches": [
    {
      "match": "<<pattern_to_match>>",
      "description": "<<description>>",
      "comment": "<<comment>>",
      "flavors": [
        {
          "flavor": "<<flavor_name>>",
          "description": "<<description>>",
          "comment": "<<comment>>",
          "reference": "<<reference>>",
          "editorconfig": {
            "<<setting>>": "<<value>>"
          }
        }
      ]
    }
  ]
}
```

Where

* `match` stands for the default files-glob the section defines; the format 
  should allow to use it to filter the defaults based on a list of files. 
  This is what goes between `[` and `]` in the editorconfig-file.
* `flavor` stands for the given flavor name; it should be used to let the 
  user choose the preferred style; the using tool might omit showing it if 
  there is only one flavor (f.e. `common` or `convention`) for the section.
* `setting` and `value` are the editorconfig-settings for that flavor; 
  they should be used to populate the editorconfig-file. 
  `value` can be a string, boolean or int value.
* `description` contains the plain-text description of that flavor; 
  it should be used as an introductory description of the flavor.
* `reference` is the reference to the source of the flavor; it should a URL 
  that leads to a authoritative description of the flavor.
* `comment` can be placed within a `<<matcher>>` and `<<flavor>>` and is 
  an optional string.


Linting
-------

To perform all the checks that are available:

```
npm install
npm run lint
```

To validate the JSON without node, there are several sites available like 
https://www.jsonschemavalidator.net/ and https://jsonschemalint.com/
