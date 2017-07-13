## Colors
- Colors need values for "day" and "night" at minimum.  
- We should make an optional "day_read" and "night_read" (or a similar affordance).

## Changes:
- I made the field names singular so they're easier to read (`tone`, `rendition`, `status` instead of `statuses`)
- Added back `column` as its own field.  (I duplicated existing rules with cases like `"rendition" : ["skim", "whole_one_column"]`)
- Added back `status` as a field and changed the text types `breaking_status`, `live_status`, etc to one type `status` with three rules

## Missing values
I wrote a test that tries to find a match for every possible card permutation.  It dumps out a LOT of text, but I think a handful of simple alterations to existing rules will fix most!  For example, we're missing a lot of rules for medium viewports when most large rules should probably just include medium as well.

