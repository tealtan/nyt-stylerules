## Colors
- Colors need values for "day" and "night" at minimum.  
- We should make an optional "day_read" and "night_read" (or a similar affordance).  Open to suggestions on structure here

## Fonts
- I made a mapping locally -- works great so far

## Changes:
- I made the field names singular so they're easier to read (`tone`, `rendition`, `status` instead of `statuses` etc)
- Added back `column` as its own field.  (I duplicated and then edited existing rules with cases like `"rendition" : ["skim", "whole_one_column"]`)
- Added back `status` as a field and changed the text types `breaking_status`, `live_status`, etc to one type `status` with three rules

## Suggestions:
- A text style called `"hidden"`?  I notice missing rules which are probably intended to indicate "no rule applies". An example is the absence of a text style for `"status" : ["default"]` (since we show nothing if status isn't breaking/live/developing)  It makes sense not to provide a text style here, but it's currently impossible to distinguish these cases from *accidentally* missing rules.  
- Tone shouldn't include "feed", there should be a value `"block" : ["feed"]`.  If block doesn't matter, of course, just leave it out.  These changes aren't in the json yet, but I intend to make them unless there are objections

## Missing values
- Byline
- Excerpt

I'm working on a test that tries to find a match for every possible card permutation.  It dumps out a LOT of text, but I think the fixes won't be that bad :) I included example output from the `headline` rules.  It seems to be missing "medium" viewport in many rules and missing a few "soft" tone rules, among others.

An example of a set which completely satisfies this test is `timestamp`!  

An example which needs 1 rule to fix is `status` (missing rules for `"status" : ["default"]`).

