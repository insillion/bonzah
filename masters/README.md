### docs

This folder contains default or Sample master data that get shipped with the software. This could include
* Rate masters
* Wordings masters - Clauses, Warranties, Conditions, Exclusions
* Lookup masters - for various dropdowns and filters in the Forms

These samples can be used to view the functioning of the product. Its advised to clear this and replace with Insurer specific master data.

**NOTE**: For Channel or Intermediary specific masters, you can configure the rater plugin (`conf.json`) to add extra columns and define the granular levels of pricing required for each Insurer. The default product being shipped does NOT include this to keep it generic for all clients.
