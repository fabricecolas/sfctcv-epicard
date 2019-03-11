# Allow to disengage duplicate detection when batch-importing 

## Persona: Large centers sending data in batch

We split "contributing centers" in two, there're:
1. those whose health practitioners register patient records one-by-one manually using CleanWeb's web UI; and
2. those who send patient records in batch using CleanWeb's import procedure.

This story focuses on type 2 users.

## Need: Disengage duplicate detection

For type 2 users of EPICARD's registry in CleanWeb, the aim is to batch-import
patient records in the registry. However this is not possible due to the
so-called duplicate detection. Here's the resulting error log appearing on the
"Simulation d'import".  
```
Erreur lors de la création de la référence patient :
01-00000001
Variable vide     ID23S2V218      Numéro de centre
```

For a center, today's approach to turn around the plugin's buggy behavior is: 
1. To request disengaging the plugin at SpecialitésMedicales;
2. Then SpecialitésMedicales requests disengaging the plugin with Tentelemed;
3. Tentelemed disengages manually the plugin and alerts SpecialitésMedicales that it's done;
4. SpecialitésMedicales alerts back the center that the plugin is disengaged;
5. The center sends the data in batch;
6. Tentelemed hears from SpecialitésMedicales that the plugin can be reengaged or, by default, it reengages it after a few days. 

In turn, this also means that for the next batch-import, the above process
needs to be reiterated. 

## Requirement

Two options: 
1. Have a duplicate-detection plugin that does not bug for batch-imports; or 
2. Give the autonomy to center's users running a batch-import to disengage that plugin when proceeding. 

