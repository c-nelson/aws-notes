The optional `Mappings` section matches a key to a corresponding set of named values. For example, if you want to set values based on a region, you can create a mapping that uses the region name as a key and contains the values you want to specify for each specific region. You use the `Fn::FindInMap` intrinsic function to retrieve values in a map.

- Templates can contain a `Mappings` object
- Which can contain many mappings
- Which map keys to values, allowing lookups
- `!FindInMap` to lookup
- Only 1 or 2 level maps

![Pasted image 20250707212620.png](_atts/Pasted%20image%2020250707212620.png)