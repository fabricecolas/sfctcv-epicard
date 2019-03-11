# The active filters are being lost when using the browser's history 

## Persona: All users. 

The described issue applies to all users of CleanWeb. 

## Need: Retain the filters selected when using the browser's history 

When selecting filters, clicking on a row, viewing the patient details, and
using the back button, then the previously set filters are reset. 

The expected behaviour would be:
1. To narrow the landing page view to the center's patients on one hand; and 
2. To preserve the filters as they were initially set.

Why? Because this way the user can review in a batch a series of patients
defined by one or more filters, and the user doesn't have to set over and over
the filters each time he starts a new session, click on save, or delete a
patient. 

## Requirement 

CleanWeb's web UI should be **statefull**:
1. Each page should be accessible with a fully defined and unique uri;
2. Each user should have its session settings cached server-side. 
