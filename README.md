# Copyright-Matching-Project

## What is this?
TL/DR: this is MARK 1 of a self-directed project to parse copyright registration and renewal data and match them together.

## Where's the data from?
The bulk of this data comes from two projects initiated by the New York Public Library (NYPL). The first is NYPL's project to extract copyright registration data from *Catalog of Copyright Entries*, an annual publication by the United States Copyright Office. The volumes were already digitized and freely available through the Internet Archive; NYPL extracted and parsed the publications as XML data. (See it [here](https://github.com/NYPL/catalog_of_copyright_entries_project).)

The second is NYPL's followup, copyright renewal data parsed from the *Catalog of Copyright Entries* as tab-delimited text, based on Project Gutenberg transcriptions, data from the Copyright Office's database for 1978–1991, and data made available by Google. (See it [here](https://github.com/NYPL/cce-renewals/).)

## Why do this?
I consider this to be a fantastic exercise in practicing not only Pandas skills, but also basic data cleaning/organization concepts.

Also, matching between the two datasets, even after converting them to Pandas dataframes, is not as straight-forward as it might seem:

1. Every registration should have a registration number, such as A56505, but these are not unique. Numbering was restarted in the *Catalog of Copyright Entries* Third Series (1947–), so there's quite a bit of overlap; for example, a registration number and date will always be required to distinguish 'A56505/1951-06-06' from 'A56505/1932-10-12'."
2. "The duplicateOf attribute indicates that the entry with the attribute contains the same information as the entry it points to and adds nothing to it. They must both have identical registration numbers and dates. \[...] All other things being equal, later duplicates should refer to earlier entries. If there are multiple duplications all duplicates should point to the same "master" registration. That entry must not have a duplicateOf attribute. So, when processing, any entries carrying a duplicateOf attribute can be skipped, since -- if an entry is truly a duplicate -- it adds nothing the copyright history of the work. When importing into a database, this will assure that there is only one row with the registration number/date combination. Renewals should be linked to registrations without the duplicateOf attribute."
3. "Often more than one registration is involved, such as when a book is first published outside the United States and has an 'interim' registration (class AI) before it's final registration. \[...] Renewal R129296 refers to both the interim registration, AI-9217, and final registration, A972756. This illustrates the importance of the id numbers, since the two original registrations have two different titles and wouldn't be clear otherwise that they are the same book."

And so on.

## Status
As of 8/13, MARK 1 is complete, finding that only ~23 percent of registered copyrights were likely renewed. This gives us an opening for MARK 2, where non-renewed (ie public domain) content may be matched with open source, publicly available versions (Project Gutenberg, Internet Archive, etc) and logged in a database for easier public access.
