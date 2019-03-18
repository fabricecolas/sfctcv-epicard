# Transcoding

This page tabs information about the export to EPICARD from Rennes' academic
hospital. It details notably: 
1. [the list of **computed attributes**](#computed-attributes);
2. [the list of **exclusion criteria**](#exclusion-criteria);
3. [some **transcoding details**](#transcoding-details).

## 1. List of computed attributes

The following table lists the transcoded attributes for EPICARD, the local ids
at Rennes' academic hospital, and some annotations. The annotations indicate
notably whether the computed attribute is:
- `{singleton, coded-as-null, coded-as-??}`, e.g., a string that's constant for all patients;
- `1-to-1`, i.e., a one-to-one relationship between a local ID and EPICARD's export;
- `calc`, i.e., an attribute that's calculated from some other local attributes;
- `transc` when a more involved transcoding algorithm combines multiple local attributes; and 
- `drift`, when an attribute's coding will drift in time and therefore needs particular attention.  

| EPICARD ID | LOCAL ID | Annotations | 
|:-----------|:---------|--------|
| `STUDY_ID`        | `'EPICARD'` | singleton |
| `COUNTRY_ID`      | `'fr'` | singleton |
| `EXTRACTION_DATE` | `System's date` |   |
| `SITE_ID`         | `'350000741_01'` | singleton |
| `SUBJECT_ID`      | `num_interv` | 1-to-1 |
| `SUBJECT_REF`     | `CONCAT('350000741_01-',  LPAD(num_interv, 8, '0'))` | calc |
| `REF_CENTRENB`    | `'350000741_01'` | singleton |
| `REF_NUMBER`      | `'350000741_01'` | singleton |
| `CENTRENB`        | `'350000741_01'` | singleton |
| `CENTRE`          | `'RENNES - HOPITAL PONTCHAILLOU'` | singleton |
| `NOM`             | `NOM_PATIENT` | 1-to-1 |
| `NOMM`            | `NOM_JF_PATIENT` | 1-to-1  |
| `PRENOM`          | `PRENOM_PATIENT` | 1-to-1  |
| `SEXE`            | `sexe` |  | 1-to-1   |   |
| `DATNAIS_D`       | `TO_CHAR(DATE_NAIS_PATIENT, 'DD')` | calc  |
| `DATNAIS_M`       | `TO_CHAR(DATE_NAIS_PATIENT, 'MM')` | calc  |
| `DATNAIS_Y`       | `TO_CHAR(DATE_NAIS_PATIENT, 'YYYY')` | calc  |
| `DATNAIS`         | `TO_CHAR(DATE_NAIS_PATIENT, 'DD/MM/YYYY')` | 1-to-1, calc  |
| `EMAIL`           | `NULL` | coded-as-null  |
| `PORT`            | `TEL` | 1-to-1  |
| `PAYSNAISS`       | Based on social security number | transc  |
| `COMNAIS`         | Based on social security number and lieunaissance | transc  |
| `COMNAISOM`       | Based on social security number | transc   |
| `PAYSNAISLEQUEL`  | `PAT_LIEUNAISSANCE` | 1-to-1  |
| `STATUSVD`        | `decode(PAT_DCD,NULL,0,1)` | 1-to-1  |
| `DATEDECP_D`      | `TO_CHAR(PAT_DATEDECES, 'DD')` | calc  |
| `DATEDECP_M`      | `TO_CHAR(PAT_DATEDECES, 'MM')` | calc  |
| `DATEDECP_Y`      | `TO_CHAR(PAT_DATEDECES, 'YYYY')` | calc  |
| `DATEDECP`        | `TO_CHAR(PAT_DATEDECES,'DD/MM/YYYY')` | calc  |
| `NBINTERVENTION`  | `PAT_NBINT_CALCUL` | 1-to-1  |
| `NBINTERVENTION_V`| `PAT_NBINT_CALCUL` | 1-to-1  |
| `DATEINTERV_D`    | `to_char(INT_DATEINTERVENTION,'DD')` | calc  |
| `DATEINTERV_M`    | `to_char(INT_DATEINTERVENTION,'MM')` | calc  |
| `DATEINTERV_Y`    | `to_char(INT_DATEINTERVENTION,'YYYY')` |calc  |
| `DATEINTERV`      | `to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` | calc  |
| `STATUS_INT`      | `NULL` | coded-as-null  |
| `STATUS_INT_V`    | `NULL` | coded-as-null  |
| `EUROSCORE`       | `NULL` | coded-as-null  |
| `EUROSCORE_V`     | `NULL` | coded-as-null  |
| `DATADM_D`        | `to_char(INT_DATEENTREE,'DD')` | calc  |
| `DATADM_M`        | `to_char(INT_DATEENTREE,'MM')` | calc  |
| `DATADM_Y`        | `to_char(INT_DATEENTREE,'YYYY')` | calc  |
| `DATADM`          | `to_char(INT_DATEENTREE,'DD/MM/YYYY')` |calc   |
| `DATINTP_D`       | `to_char(INT_DATEINTERVENTION,'DD')` | calc  |
| `DATINTP_M`       | `to_char(INT_DATEINTERVENTION,'MM')` | calc  |
| `DATINTP_Y`       | `to_char(INT_DATEINTERVENTION,'YYYY')` | calc  |
| `DATINTP`         | `to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` | calc  |
| `AGE`             | `AGE_CALCUL` | 1-to-1  |
| `AGE_V`           | `AGE_CALCUL` | 1-to-1  |
| `EUROSCORE_AGE`   | `NULL` | coded-as-null  |
| `EUROSCORE_AGE_V` | `NULL` | coded-as-null  |
| `POIDS`           | `int_poids` | 1-to-1  |
| `POIDS_V`         | `int_poids` | 1-to-1  |
| `TAILLE`          | `int_taille` | 1-to-1  |
| `TAILLE_V`        | `int_taille` | 1-to-1  |
| `SURF_COPR`       | `ROUND(INT_SurfCorp_calcul,0.01)` | calc  |
| `SURF_COPR_V`     | `ROUND(INT_SurfCorp_calcul,0.01)` | calc  |
| `IMC`             | `ROUND(INT_Poids / ( (INT_Taille/100)*(INT_Taille/100)),0.01)` | calc |
| `IMC_V`           | `ROUND(INT_Poids / ( (INT_Taille/100)*(INT_Taille/100)),0.01)` | calc |
| `CREAPREOP`       | `ipo_creat` | 1-to-1 |
| `CREAPREOP_V`     | `ipo_creat` | 1-to-1 |
| `CLEARANCE`       | Based on patient's gender | transc |
| `END CLEARANCE_V` | based on patient's gender (copied) | transc |
| `DIAL`            | based renal insufficiency | transc |
| `TDIABPREOP`      | based on diabetes risk | transc |
| `EUROSCORE_DIABETE` | `NULL` | coded-as-null  |
| `DIAB`            | `ipo_risq_diabete` | 1-to-1 |
| `BPCO`            | `IPO_Patho_InsResp` | 1-to-1 |
| `ENDOCARA`        | Based on etiology of endocarditis (diagnostics) | transc |
| `ENDOSTER`        | Based on etiology of endocarditis (diagnostics) | transc |
| `NEUROMUSC`       | `IPO_Patho_DeficitNeuro` | 1-to-1 |
| `APCVIAP`         | `IPO_Patho_ArtheritVX` | 1-to-1 |
| `AMI`             | `IPO_Patho_ArtheritMI` | 1-to-1 |
| `AORTIAP`         | `IPO_PATHO_ARTHERITMI` | 1-to-1  |
| `ARTEXTR`         |  | transc |
| `ATCD`            |  | transc |
| `NOM_OPCAR`       | Based on previous intervention and reintervention | transc |
| `NOM_OPCAR_V`     | Based on previous intervention and reintervention (copied) | transc |
| `NYHA`            | `ipo_nyha` | 1-to-1 |
| `ANGOR`           | `ipo_angor_instable` | 1-to-1 |
| `IDM_90`          | `IEC_INFARCTUS_90J` | 1-to-1 |
| `TVFV`            | Based on iec_ecgrythme | transc |
| `ANUOLI`          | `int_choc` | 1-to-1 |
| `INOTR`           | `INT_INOTROP` | 1-to-1 |
| `BCP_PREOP`       | `INT_UrgCPBIA` | 1-to-1 |
| `ECMO_ECLS`       | `INT_ASSMECA` | 1-to-1 |
| `INC_PREOP`       | `int_intub` | 1-to-1 |
| `MC_PREOP`        | `INT_masscard` | 1-to-1 |
| `ETATPREOP`       |  | transc |
| `FE`              | `iec_echofe` | 1-to-1 |
| `FE_V`            | `iec_echofe` | 1-to-1 |
| `FE_CLASSE`       | Based on `iec_echofe` | transc |
| `PAPS`            | `IEC_EchoPaSyst` | 1-to-1 |
| `PAPS_V`          | `IEC_EchoPaSyst` | 1-to-1 |
| `PAPS_CLASSE`     | Based on `IEC_EchoPaSyst` | transc |
| `DEGURG`          | `int_urgence` | 1-to-1 |
| `COMINT`          | Transc. details [below](#TRANSCODING_COMINT)  | transc |
| `CHIRAO`          | `igs_chiaort` | 1-to-1 |
| `MARFAN`          | Based on `IDG_Etio_Marfan` | transc |
| `CIVPI`           | Based on `igs_chi_fermeture_civa` | transc |
| `NOMB_VCPA`       | | transc |
| `STEN`            | Based on `iec_corog_degre` |  transc |
| `ANTANC`          | Based on `ian_dateptca1,2,3,4` |  transc |
| `INSAOR`          | |  transc |
| `ETIOAMTP_C1`     | |  transc |
| `ETIOAMTP_C2`     | |  transc |
| `ETIOAMTP_C3`     | |  transc |
| `ETIOAMTP_C4`     | |  transc |
| `RETAOR`          | `decode(idg_lesionvalv_ra,NULL,0,1)` |   |
| `RETMIT`          | `decode(idg_lesionvalv_rm,NULL,0,1)` |   |
| `RETTRI`          | `decode(idg_lesionvalv_rt,NULL,0,1)` |   |
| `RETPULM`         | `decode(idg_lesionvalv_rp,NULL,0,1)` |   |
| `HTA`             | `ipo_risq_hta` | 1-to-1 |
| `HCHOL`           | `IPO_Risq_Dyslip` | 1-to-1  |
| `TAVK`            | Based on `ipo_patho_anticoag` | transc |
| `TAA`             | Based on `ipo_patho_antiag` | transc |
| `DOURAA`          | Coded as missing (`2`) | coded-as-2  |
| `NINCEC`          |        | transc  |
| `ATCDF`           | `NULL` | coded-as-null |
| `DOSSIER`         | `NULL` | coded-as-null |
| `COMPAT`          | `NULL` | coded-as-null |
| `CHIRAV`          | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `CHIRAV_V`        | `NULL` | coded-as-null, EPICARD_v1 (obsolete) | 
| `INTMCEC`         | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `INTMCEC_V`       | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `EUROSCORE1`      | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `EUROSCORE1_V`    | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `EUROSCOREL`      | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `EUROSCOREL_V`    | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `CPBIA_PEROP`     | `NULL` | coded-as-null, EPICARD_v1 (obsolete) |
| `DATINT_D`        | `to_char(INT_DATEINTERVENTION,'DD')` | calc  |
| `DATINT_M`        | `to_char(INT_DATEINTERVENTION,'MM')` | calc  |
| `DATINT_Y`        | `to_char(INT_DATEINTERVENTION,'YYYY')` | calc  |
| `DATINT`          | `to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` | calc  |
| `CODCHIR1`        | 1st surgeon's first and last names | transc, drift |
| `NBRPPS1`         | 1st surgeon's RPPS | transc, drift |
| `CODCHIR2`        | 2nd surgeon's first and last name | transc, drift |
| `NBRPPS2`         | 2nd surgeon's RPPS | transc, drift |
| `TYPECHIR_C1`     | `DECODE(igs_chicor, NULL, NULL, 1)` | 1-to-1 |
| `TYPECHIR_C2`     |     | transc |
| `TYPECHIR_C3`     | `DECODE(IGS_CHIAORT, NULL, NULL, 1)` | 1-to-1 |
| `DURCLAMP`        | `int_tpsclamp` | 1-to-1 |
| `DURCLAMP_V`      | `int_tpsclamp` | 1-to-1 |
| `DURCEC`          | `int_tpscec` | 1-to-1 |
| `DURCEC_V`        | `int_tpscec` | 1-to-1 |
| `PROTCER`         |  | transc |
| `GVA`             |  | transc |
| `PROTCERA_C1`     | Based on `INT_PERFCEREB` | transc |
| `PROTCERA_C2`     | Based on `int_itgarretcirc` | transc  |
| `PROTCERA_C3`     | Based on `INT_PERFCEREB` | transc  |
| `VOIESAB_C1`      | Based on `INT_Voie` | transc  |
| `VOIESAB_C2`      | Based on `INT_Voie` | transc  |
| `VOIESAB_C3`      | Based on `IGS_CHIENDO` | transc  |
| `VOIESAB_C4`      | Based on `INT_Voie` | transc  |
| `VOIESAB_C5`      | Based on `INT_Voie` | transc  |
| `VOIESAB_C6`      | Based on `INT_Voie` | transc |
| `VOIESAB_C7`      | Based on `INT_Voie` | transc  |
| `VOIESAB_C8`      | `NULL` | coded-as-null  |
| `VOIESAB_C9`      | `NULL` |  coded-as-null |
| `VOIESAB_C11` | `NULL` |coded-as-null   |
| `VOIESAB_C10` | Based on `INT_Voie` | transc |
| `SIVOIES_1` |  | transc |
| `SIVOIES_2` |  | transc |
| `SIVOIES_3` |  | transc |
| `NTHCENTRE` | `NULL` |coded-as-null   |
| `NTCA` |  | transc |
| `NTCA_V` | | transc |
| `NACCA` |  | transc |
| `NACCA_V` |  | transc |
| `NTCV` | | transc |
| `NTCV_V` | | transc |
| `NACCV` |  | transc |
| `NACCV_V` |  | transc |
| `CTAIRECORO` | `''` |   |
| `GESTEV_C1` | | transc |
| `GESTEV_C2` | | transc  |
| `GESTEV_C3` | | transc  |
| `GESTEV_C4` | | transc  |
| `CVAO` | | transc  |
| `AORVALO` | | transc  |
| `NUMSERA` | `IGS_ChiValvaire_RVANSerie` | 1-to-1 |
| `NUMLOTA` | `NULL` | coded-as-null  |
| `GVMO` |  | transc  |
| `FABRICANTM` | | transc  |
| `MODELEM` | | transc  |
| `TAILLEM` | | transc  |
| `NUMSERM` | `IGS_ChiValvaire_RVMNSerie` | 1-to-1  |
| `NUMLOTM` | `NULL` | coded-as-null  |
| `GVTO` |  | transc  |
| `TRIVALO` | Based on `IGS_ChiValvaire_RVTType` | transc |
| `FABRICANTT` | | transc |
| `MODELET` | Based on `IGS_ChiValvaire_RVTType` | transc |
| `TAILLET` | Based on `IGS_ChiValvaire_RVTType` `IGS_ChiValvaire_RVTTaille` | transc |
| `NUMSERT` | `IGS_ChiValvaire_RVTNSerie` | 1-to-1 |
| `NUMLOTT` | `NULL` | coded-as-null  |
| `GVPO` | Based on `IGS_ChiValvaire_RVPType` | transc |
| `PULMVALO` | Based on `IGS_ChiValvaire_RVPType` | transc |
| `FABRICANTP` | Based on `IGS_ChiValvaire_RVPType` | transc |
| `MODELEP` | Based on `IGS_ChiValvaire_RVPType` | transc |
| `TAILLEP` | Based on `IGS_ChiValvaire_RVPType` `IGS_ChiValvaire_RVPTaille` | transc |
| `NUMSERP` | `IGS_ChiValvaire_RVPNSerie` | 1-to-1 |
| `NUMLOTP` | `NULL` | coded-as-null  |
| `CTAIREVALV` | `NULL` | coded-as-null  |
| `DIAGO` |  | transc |
| `GESTEO` | | transc  |
| `LOCO_C1` | `IGS_ChiAort_AS` | 1-to-1 |
| `LOCO_C2` | `IGS_ChiAort_AS` | 1-to-1 |
| `LOCO_C3` | `IGS_ChiAort_Crosse` | 1-to-1 |
| `LOCO_C4` | `IDG_RuptAO`  `IGS_ChiAort` | transc |
| `LOCO_C5` | `IGS_ChiAort_DE` | 1-to-1 |
| `LOCO_C6` | `NULL` | coded-as-null  |
| `STENT` | `IGS_ChiAort_DE` | 1-to-1 |
| `STENTO` | `IGS_ChiAort_Crosse` | 1-to-1 |
| `NB_TUBE` | `NULL` | coded-as-null  |
| `FABRICANTCA1` | `NULL` | coded-as-null  |
| `MODELECA1` | `NULL` | coded-as-null  |
| `TAILLECA1` | `NULL` | coded-as-null  |
| `NUMSERCA1` | `NULL` | coded-as-null  |
| `NUMLOTCA1` | `NULL` | coded-as-null  |
| `FABRICANTCA2` | `NULL` | coded-as-null  |
| `MODELECA2` | `NULL` | coded-as-null  |
| `TAILLECA2` | `NULL` | coded-as-null  |
| `NUMSERCA2` | `NULL` | coded-as-null  |
| `NUMLOTCA2` | `NULL` | coded-as-null  |
| `FABRICANTCA3` | `NULL` | coded-as-null  |
| `MODELECA3` | `NULL` | coded-as-null  |
| `TAILLECA3` | `NULL` | coded-as-null  |
| `NUMSERCA3` | `NULL` | coded-as-null  |
| `NUMLOTCA3` | `NULL` | coded-as-null  |
| `PROTVO` |  | transc |
| `PROTAOTYPE` |  | transc |
| `TAILLECA4` | `IGS_ChiAort` | transc |
| `NUMSERCA4` | `IGS_ChiAort` | transc |
| `NUMLOTCA4` | `NULL` | coded-as-null  |
| `COMM` | `NULL` |coded-as-null   |
| `CHIRDIV_C1` | `igs_chi_fermeture_civa` | 1-to-1  |
| `CHIRDIV_C2` | `igs_chi_fermeture_civp` | 1-to-1  |
| `CHIRDIV_C3` | `igs_chiaut_cmo` | 1-to-1  |
| `CHIRDIV_C4` | `igs_chi_resanevrisme` | 1-to-1  |
| `CHIRDIV_C5` | `igs_chi_complication_rupt` | 1-to-1  |
| `CHIRDIV_C6` | Based on `INT_BasCgx` `AGE_CALCUL` | transc |
| `CHIRDIV_C7` | `igs_chiaut_emboliepulm` | 1-to-1  |
| `CHIRDIV_C8` | `igs_chi_complication_rythme` | 1-to-1  |
| `CHIRDIV_C9` | `igs_chiaut_tum` | 1-to-1  |
| `CHIRDIV_C10` | `idg_coeurcontusion` | 1-to-1  |
| `CHIRDIV_C11` | `idg_coeurplaie` | 1-to-1  |
| `CHIRDIV_C12` | `NULL` | coded-as-null  |
| `CHIRDIV_C13` | `igs_chiaut_gref` | 1-to-1  |
| `CHIRDIV_C14` | `NULL` | coded-as-null  |
| `CHIRDIV_C15` | `NULL` | coded-as-null  |
| `CHIRDIV_C16` | `NULL` |  coded-as-null |
| `CHIRDIV_C17` | `NULL` | coded-as-null  |
| `CHIRDIV_C18` | `IGS_CHIAUT_DEFIBRILL` | 1-to-1  |
| `CHIRDIV_C19` |  | transc |
| `AUTRCHIT` | `NULL` |coded-as-null   |
| `AUTRCHIRCVO_C1` | `IGS_CHIAUT_ASSOC` | 1-to-1  |
| `AUTRCHIRCVO_C2` | `NULL` |coded-as-null   |
| `AUTRCHIRNCTO_C1` | `NULL` |coded-as-null   |
| `AUTRCHIRNCTO_C2` | `IGS_CHIAUT_ASSOC` | 1-to-1  |
| `DRECMOIS_C1` | `NULL` |coded-as-null   |
| `DRECMOIS_C2` | `NULL` |coded-as-null   |
| `DRECMOIS_C3` | `IGS_CHIAUT_LONGDUREE` | 1-to-1  |
| `TRANS` | | transc |
| `GRAVGLOB` | `NULL` |coded-as-null   |
| `REINTERV` |  | transc |
| `REINTCECO` | `iso_REINT` | transc |
| `COMPLL_C1` | `ISO_Saignt` | 1-to-1 |
| `COMPLL_C2` | `iso_reprisetamp` | 1-to-1  |
| `COMPLL_C3` | `ISO_DOBU` | 1-to-1  |
| `COMPLL_C4` |  | transc |
| `COMPLL_C5` |  | transc |
| `COMPLL_C6` |  | transc |
| `COMPLL_C7` | `ISO_ECGRythme` | 1-to-1  |
| `COMPLL_C8` | `iso_insrenale` | 1-to-1  |
| `COMPLL_C9` | `iso_ventilprolonge` | 1-to-1  |
| `COMPLL_C10` | `NULL` |coded-as-null   |
| `COMPLL_C30` | `NULL` |coded-as-null   |
| `COMPLL_C11` | `ISO_Desunion` | 1-to-1  |
| `COMPLL_C12` | `iso_sepsimedia` | 1-to-1  |
| `COMPLL_C13` | `NULL` |coded-as-null   |
| `COMPLL_C14` | Based on `ISO_ECHOSurfA` `ISO_ECHOSurfM` | calc  |
| `COMPLL_C15` | `ISO_CPProthese_DYS` | 1-to-1  |
| `COMPLL_C16` | `iso_hemorragiedigest` | 1-to-1  |
| `COMPLL_C17` | `NULL` |coded-as-null   |
| `COMPLL_C18` | `iso_cpneuro_avc = 1` | 1-to-1  |
| `COMPLL_C19` | `iso_cpneuro_avc = 2` | 1-to-1  |
| `COMPLL_C20` | `iso_cpneuro_coma` | 1-to-1  |
| `COMPLL_C21` | `ISO_ECGRythme` | 1-to-1  |
| `COMPLL_C22` | `ISO_ECGCond_BAV` | 1-to-1  |
| `COMPLL_C23` | `iso_cond_pace` | 1-to-1  |
| `COMPLL_C24` | `NULL` |coded-as-null   |
| `COMPLL_C25` | `ISO_AccidentHemo` | 1-to-1 |
| `COMPLL_C26` | `ISO_AllHeparine` | 1-to-1 |
| `COMPLL_C27` | `NULL` |coded-as-null   |
| `COMPLL_C28` | `NULL` | coded-as-null  |
| `COMPLL_C29` | `NULL` |coded-as-null   |
| `AUTRCOMT`    | `NULL` |coded-as-null   |
| `DATESORT_D` | `to_char(INT_DateSortie,'DD')` | calc |
| `DATESORT_M` | `to_char(INT_DateSortie,'MM')` | calc |
| `DATESORT_Y` | `to_char(INT_DateSortie,'YYYY')` | calc |
| `DATESORT` | `to_char(INT_DateSortie,'DD/MM/YYYY')` | calc |
| `STAT` | `decode(PAT_DCD,NULL,0,1)` | calc |
| `DEC30J` |  | calc |
| `DATEDEC_D` | `to_char(pat_datedeces,'DD')` | calc |
| `DATEDEC_M` | `to_char(pat_datedeces,'MM')` | calc |
| `DATEDEC_Y` | `to_char(pat_datedeces,'YYYY')` | calc |
| `DATEDEC` | `to_char(pat_datedeces,'DD/MM/YYYY')` | calc |
| `DELDEC` | | transc |
| `DELDEC_V` | | transc |
| `CAUSEDEATH` | | transc |
| `CTAIREDECE` | `NULL` |coded-as-null   |
| `EILS_TITTRE1` | `NULL` |coded-as-null   |
| `EILS_TITTRE_L1` | `NULL` |coded-as-null   |
| `TITRE_EILS_AUTT_L1` | `NULL` | coded-as-null  |
| `RISQ_EILST_L1` | `NULL` | coded-as-null  |
| `AUTRRISQT_L1` | `NULL` | coded-as-null  |
| `DEFAILLANCE_EILST_L1` | `NULL` | coded-as-null  |
| `MOMENT_EILST_L1` | `NULL` | coded-as-null  |
| `EILS_DESCRT_L1` | `NULL` | coded-as-null  |
| `DATEDN_F1_D` | `NULL` | coded-as-null  |
| `DATEDN_F1_M` | `NULL` | coded-as-null  |
| `DATEDN_F1_Y` | `NULL` | coded-as-null  |
| `DATEDN_F1` | `NULL` | coded-as-null  |
| `TYPECONSULTACTE_F1` | `NULL` | coded-as-null  |
| `STATUT_F1` | `NULL` | coded-as-null  |
| `RCP_F1` | `NULL` | coded-as-null  |
| `TRT_FAIT_F1` | `NULL` | coded-as-null  |
| `PROTOC_YN_F1` | `NULL` | coded-as-null  |
| `COMMENT_DN_F1` | `NULL` |coded-as-null   |
| `DECAPRESSORT` |  | transc |
| `OCOMPL` | | transc, drift|
| `CLEARDIAL_CLASSE` | | transc |
| `ETIOA` |  | transc |
| `INSMIT` |  | transc |
| `ETIOM` |  | transc |
| `INSTRI` |  | transc |
| `ETIOT` |  | transc |
| `INSPULM` |  | transc |
| `ETIOP` |  | transc |
| `TYPECHIR_C4` | | transc |
| `CEC` | `int_coeurbattant` | 1-to-1 |
| `FABRICANTA` | Based on `IGS_ChiValvaire_RVAType` | transc, drift |
| `MODELEA` | Based on `IGS_ChiValvaire_RVAType` | transc, drift  |
| `TAILLEA` | Based on `IGS_ChiValvaire_RVAType and Taille` | transc, drift |
| `MITVALO` | Based on `Trasncoding based on RVMType` | transc, drift |
| `FABRICANTCA4` | Based on `IGS_ChiValvaire_RVAType` | transc, drift |
| `MODLECA4` | Based on `IGS_ChiValvaire_RVAType` | transc, drift |
| `NTAC` | `NTCV_V+NACCV_V` | calc |
| `NTAC_V` | `NTCV_V+NACCV_V` | calc |

## 2. List of exclusion criteria <a name="exclusion-criteria"></a>

Patients matching one or more of the following criteria are not sent to EPICARD: 
1. No endoprostheses (IGS_CHIENDO);
2. No re-operated patient (redux);
3. No followed-up patients (returns only the first intervention row_number == 1);
4. No incoherent weight (>250). 

## 3. Transcoding details <a name="transcoding-details"></a> 

### Attribute *COMINT* (EPICARD) <a name="TRANSCODING_COMINT"></a> 

```
     IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=0 AND (Chi.Cor.>0)>0 THEN 1 (Pontage isolé)
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)=1 AND (Chi.Cor.>0)=0 THEN 2 (Un seul geste autre que pontage)
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)=2 THEN 3 (Double geste (double valve ou pont+valve))
ELSE IF (Chi.Valv.>0)+(Chi.Compl.Infar.>0)+(Chi.Ao.>0)+(Chi.Endo.>0)+(Chi.Autres>0)+(Indic.Congén.>0)    +  (Chi.Cor.>0)>2 THEN 4 (Triple geste ou plus)
```

Notations:
- `Indic.Congén.` := Intervention due to a birth defect (congenital disorder)
