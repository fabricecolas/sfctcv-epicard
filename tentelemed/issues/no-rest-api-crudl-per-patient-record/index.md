# No access to a REST API to manage patient records 

## Persona: Large centers sending data in batch

We split "contributing centers" in two, there're:
1. those whose health practitioners register patient records one-by-one manually using CleanWeb's web UI; and
2. those who send patient records in batch using CleanWeb's import procedure.

This story focuses on type 2 users.

## Need: Propagate live atomic-changes from the local registry into the remote registry

Our local registry's patient records have a lifecycle that starts when
patients are first operated and when the operation's characteristics are
recorded using a series of in-house developed surveys. These are then
digitized by an epidemiologist who verifies, complete, and enter the
information into our system. 

This is how a patient enters the system, however a patient's records will see
its information change over time, notably when more follow-up data is
collected. The challenge is therefore to propagate a patient's updated info
from the local registry back to the national registry.

## Requirement 

A REST API endpoint with full CRUDL operations to manage a patient record completely. 
