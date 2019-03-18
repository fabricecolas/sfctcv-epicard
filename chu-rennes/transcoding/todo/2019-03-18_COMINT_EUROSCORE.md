# EuroScore too high: Due to transcoding of COMINT?

## Problem

It seems the EuroScore is too high for many patients from Rennes.

## Possible causes
1. Locally, forms are improperly entered;
2. Transcoding of `COMINT` is inadequate; or  
3. Transcoding of `CHIRDIV` or `TYPECHIR` is inadequate.

## How to address the problem

Review the **EuroScore guidelines** to code the complexity of a surgical
intervention, and check that:
1. 1+ coronary artery bypass graft is coded as 1 whenever 1+ bypasses are done;
2. `CHIRDIV` and `TYPECHIR` are properly coding all the interventions types,
thereby not letting one understand that there's only one intervention when
there're two;  
3. One surgical intervention on a valve = 1; and 
4. More valve interventions count for 2+; 

One proposed changed (to be reviewed) is to move from the indicator `(Chi.Valv.>0)` to the count `N(Chi.Valv.)`:
``` /* Current */
     IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=0 AND (Chi.Cor.>0)>0 THEN 1 (Pontage isolé)
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=1 AND (Chi.Cor.>0)=0 THEN 2 (Un seul geste autre que pontage)
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)=2 THEN 3 (Double geste (double valve ou pont+valve))
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)>2 THEN 4 (Triple geste ou plus)
```
``` /* New */
     IF N(Chi.Valv.)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=0 AND (Chi.Cor.>0)>0 THEN 1 (Pontage isolé)
ELSE IF N(Chi.Valv.)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=1 AND (Chi.Cor.>0)=0 THEN 2 (Un seul geste autre que pontage)
ELSE IF N(Chi.Valv.)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)=2 THEN 3 (Double geste (double valve ou pont+valve))
ELSE IF N(Chi.Valv.)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)>2 THEN 4 (Triple geste ou plus)
```
