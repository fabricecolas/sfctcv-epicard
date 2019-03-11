# The investigator is not the operating surgeon: Import procedure makes bad assumption 

## Persona: Large centers sending data in batch

We split "contributing centers" in two, there're:
1. those whose health practitioners register patient records one-by-one manually using CleanWeb's web UI; and
2. those who send patient records in batch using CleanWeb's import procedure.

This story focuses on type 2 users.

## Need: Get operating surgeon's name from intervention's record and not from the import form

It seems Tentelemed's import procedure considers that the operating surgeon is
equivalent to the principal investigator making the batch data import on
EPICARD. However this assumption is invalid. As a workaround, Tentelemed
suggests to make as many imports as there are of operating surgeons for 
each batch import—obviously, this is not inadequate.  

## Requirement

1. Do not assume that the import investigator is the operating surgeon;
2. Retrieve from an intervention's record the operating surgeon. 
