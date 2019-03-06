# Detect BOM in batch-import

## Persona: Large centers sending data in batch

We split "contributing centers" in two, there're:
1. those whose health practitioners register patient records one-by-one manually using CleanWeb's web UI; and
2. those who send patient records in batch using CleanWeb's import procedure.

This story focuses on type 2 users.

## Need: Detect if first file's character is a Byte Order Mark (BOM)

A hidden unicode character appears at the beginning of the CSV files—see below
the character by character diff (truncated): 
```
<U+FEFF>"STUDY_ID"; [...] ;"EILS_TITTRE1"^M
```
The U+FEFF unicode character is a 'ZERO WIDTH NO-BREAK SPACE'. By default Excel
adds it. And in the Windows-based database export program, it's an option
enabled by default and referred to as "Insert BOM". 

To illustrate this problem this folder contains two example subfolders: 
1. [`issue`](/issue) contains examples files with the BOM  that fail the tests despite being correctly structured.  
2. [`test`](/test)  contains examples files sent by SpecialitesMedicalesno, that have no BOM, and which pass all tests; whereas

## Requirement: No U+FEFF (BOM) at the beginning of the CSV files.

Two options:
1. Test existence of character at file's beginning and delete it ; or
2. Reveal that the CSV isn't in the right format, indicating that a unicode character is at the file's beginning.
