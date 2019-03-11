# Empty a center from its patients 

## Persona: Large centers sending data in batch

We split "contributing centers" in two, there're:
1. those whose health practitioners register patient records one-by-one manually using CleanWeb's web UI; and 
2. those who send patient records in batch using CleanWeb's import procedure. 

- This story focuses on type 2 users. 

## Need: Empty a center from its patients

For type 2 users of EPICARD's registry in CleanWeb, the aim is to develop a
so-called *transcoding*, i.e., an algorithm written as a software that sources
data from an in-house developed information system, and that maps its values
onto those expected by the target registry. 

As a transcoding relies on technical, logical, and scientific considerations,
it's a complicated software piece to make. Before its initial version is setup,
it requires trial and errors. Over the long-term, minor corrections or
extensions are going to be applied to the transcoding. 

While a transcoding's development is therefore iterative, today's CleanWeb does
not provide yet the **base operations to manage a center's patients**, e.g., the
ability **to drop (truncate, empty) all of a center's patients**. Instead,
CleanWeb only allows to remove or update patient records one-by-one, which 
works for type 1 of CleanWeb but not for type 2 users that manage high
numbers of patients.

## Requirement

Empty a center of its patients (DELETE-*).
