# Copyright-Matching-Project

## What is this?
TL/DR: this is MARK 1 of a self-directed project to parse copyright registration and renewal data and match them together.

## Where's the data from?
The bulk of this data comes from two projects initiated by the New York Public Library (NYPL). The first is NYPL's project to extract copyright registration data from *Catalog of Copyright Entries*, an annual publication by the United States Copyright Office. The volumes were already digitized and freely available through the Internet Archive; NYPL extracted and parsed the publications as XML data. (See it [here](https://github.com/NYPL/catalog_of_copyright_entries_project).)

The second is NYPL's followup, copyright renewal data parsed from the *Catalog of Copyright Entries* as tab-delimited text, based on Project Gutenberg transcriptions, data from the Copyright Office's database for 1978–1991, and data made available by Google. (See it [here](https://github.com/NYPL/cce-renewals/).)

## Why do this?
I consider this to be a fantastic exercise in practicing not only Pandas skills, but also basic data cleaning/organization concepts.

Matching between the two datasets, even after converting them to Pandas dataframes, is not as straight-forward as it seems. 
