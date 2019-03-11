# Transcoding

- [Computed attributes](#computed-attributes)
- [Exclusion criteria](#exclusion-criteria)

## Computed attributes


| EPICARD ID | LOCAL ID | 1-to-1 | Transc. | 
|------------|----------|--------|---------|
| `INUM_PATIENT`    | ` num_patient` |  |   |
| `STUDY_ID`        | ` 'EPICARD'` |  |   |
| `COUNTRY_ID`      | ` 'fr'` |  |   |
| `EXTRACTION_DATE` | ` System's date` |  |   |
| `SITE_ID` | ` '350000741_01'` |  |   |
| `SUBJECT_ID` | ` num_interv` |  |   |
| `SUBJECT_REF` | ` CONCAT('350000741_01-',  LPAD(num_interv, 8, '0'))` |  |   |
| `REF_CENTRENB` | ` '350000741_01'` |  |   |
| `REF_NUMBER` | ` '350000741_01'` |  |   |
| `CENTRENB` | ` '350000741_01'` |  |   |
| `CENTRE` | ` 'RENNES - HOPITAL PONTCHAILLOU'` |  |   |
| `NOM` | ` NOM_PATIENT` |  |   |
| `NOMM` | ` NOM_JF_PATIENT` |  |   |
| `PRENOM` | ` PRENOM_PATIENT` |  |   |
| `SEXE` | ` sexe` |  |   |
| `DATNAIS_D` | ` TO_CHAR(DATE_NAIS_PATIENT, 'DD')` |  |   |
| `DATNAIS_M` | ` TO_CHAR(DATE_NAIS_PATIENT, 'MM')` |  |   |
| `DATNAIS_Y` | ` TO_CHAR(DATE_NAIS_PATIENT, 'YYYY')` |  |   |
| `DATNAIS` | ` TO_CHAR(DATE_NAIS_PATIENT, 'DD/MM/YYYY')` |  |   |
| `EMAIL` | ` NULL` |  |   |
| `PORT` | ` TEL` |  |   |
| `PAYSNAISS` | ` Transcoding based on social security number` |  |   |
| `COMNAIS` | ` Transcoding based on social security number and lieunaissance` |  |   |
| `COMNAISOM` | ` Transcoding based on social security number` |  |   |
| `PAYSNAISLEQUEL` | ` PAT_LIEUNAISSANCE` |  |   |
| `STATUSVD` | ` decode(PAT_DCD,NULL,0,1)` |  |   |
| `DATEDECP_D` | ` TO_CHAR(PAT_DATEDECES, 'DD')` |  |   |
| `DATEDECP_M` | ` TO_CHAR(PAT_DATEDECES, 'MM')` |  |   |
| `DATEDECP_Y` | ` TO_CHAR(PAT_DATEDECES, 'YYYY')` |  |   |
| `DATEDECP` | ` TO_CHAR(PAT_DATEDECES,'DD/MM/YYYY')` |  |   |
| `NBINTERVENTION` | ` PAT_NBINT_CALCUL` |  |   |
| `NBINTERVENTION_V /* num_interv */` | ` PAT_NBINT_CALCUL` |  |   |
| `DATEINTERV_D` | ` to_char(INT_DATEINTERVENTION,'DD')` |  |   |
| `DATEINTERV_M` | ` to_char(INT_DATEINTERVENTION,'MM')` |  |   |
| `DATEINTERV_Y` | ` to_char(INT_DATEINTERVENTION,'YYYY')` |  |   |
| `DATEINTERV` | ` to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` |  |   |
| `STATUS_INT` | ` NULL` |  |   |
| `STATUS_INT_V` | ` NULL` |  |   |
| `EUROSCORE` | ` NULL` |  |   |
| `EUROSCORE_V` | ` NULL` |  |   |
| `DATADM_D` | ` to_char(INT_DATEENTREE,'DD')` |  |   |
| `DATADM_M` | ` to_char(INT_DATEENTREE,'MM')` |  |   |
| `DATADM_Y` | ` to_char(INT_DATEENTREE,'YYYY')` |  |   |
| `DATADM` | ` to_char(INT_DATEENTREE,'DD/MM/YYYY')` |  |   |
| `DATINTP_D` | ` to_char(INT_DATEINTERVENTION,'DD')` |  |   |
| `DATINTP_M` | ` to_char(INT_DATEINTERVENTION,'MM')` |  |   |
| `DATINTP_Y` | ` to_char(INT_DATEINTERVENTION,'YYYY')` |  |   |
| `DATINTP` | ` to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` |  |   |
| `AGE` | ` AGE_CALCUL` |  |   |
| `AGE_V` | ` AGE_CALCUL` |  |   |
| `EUROSCORE_AGE` | ` NULL` |  |   |
| `EUROSCORE_AGE_V` | ` NULL` |  |   |
| `POIDS` | ` int_poids` |  |   |
| `POIDS_V` | ` int_poids` |  |   |
| `TAILLE` | ` int_taille` |  |   |
| `TAILLE_V` | ` int_taille` |  |   |
| `SURF_COPR` | ` ROUND(INT_SurfCorp_calcul,0.01)` |  |   |
| `SURF_COPR_V` | ` ROUND(INT_SurfCorp_calcul,0.01)` |  |   |
| `IMC` | ` ROUND(INT_Poids / ( (INT_Taille/100)*(INT_Taille/100)),0.01)` |  |   |
| `IMC_V` | ` ROUND(INT_Poids / ( (INT_Taille/100)*(INT_Taille/100)),0.01)` |  |   |
| `CREAPREOP` | ` ipo_creat` |  |   |
| `CREAPREOP_V` | ` ipo_creat` |  |   |
| `CLEARANCE` | ` Transcoding based on patient's gender` |  |   |
| `END CLEARANCE_V` | ` Transcoding based on patient's gender (copied)` |  |   |
| `DIAL` | ` Transcoding based renal insufficiency` |  |   |
| `TDIABPREOP` | ` Transcoding based on diabetes risk` |  |   |
| `EUROSCORE_DIABETE` | ` NULL` |  |   |
| `DIAB` | ` ipo_risq_diabete` |  |   |
| `BPCO` | ` IPO_Patho_InsResp` |  |   |
| `ENDOCARA` | ` Transcoding based on etiology of endocarditis (diagnostics)` |  |   |
| `ENDOSTER` | ` Transcoding based on etiology of endocarditis (diagnostics)` |  |   |
| `NEUROMUSC` | ` IPO_Patho_DeficitNeuro` |  |   |
| `APCVIAP` | ` IPO_Patho_ArtheritVX` |  |   |
| `AMI` | ` IPO_Patho_ArtheritMI` |  |   |
| `AORTIAP` | ` IPO_PATHO_ARTHERITMI` |  |   |
| `ARTEXTR` | ` Transcoding` |  |   |
| `ATCD` | ` Whether there's been a previous intervention (transcoding)` |  |   |
| `NOM_OPCAR` | ` Transcoding based on previous intervention and reintervention` |  |   |
| `NOM_OPCAR_V` | ` Transcoding based on previous intervention and reintervention (copied)` |  |   |
| `NYHA` | ` ipo_nyha` |  |   |
| `ANGOR` | ` ipo_angor_instable` |  |   |
| `IDM_90` | ` IEC_INFARCTUS_90J` |  |   |
| `TVFV` | ` Transcoding based on iec_ecgrythme` |  |   |
| `ANUOLI` | ` int_choc` |  |   |
| `INOTR` | ` INT_INOTROP` |  |   |
| `BCP_PREOP` | ` INT_UrgCPBIA` |  |   |
| `ECMO_ECLS` | ` INT_ASSMECA` |  |   |
| `INC_PREOP` | ` int_intub` |  |   |
| `MC_PREOP` | ` INT_masscard` |  |   |
| `ETATPREOP` | ` Transcoding` |  |   |
| `FE` | ` iec_echofe` |  |   |
| `FE_V` | ` iec_echofe` |  |   |
| `FE_CLASSE` | ` Transcoding based on iec_echofe` |  |   |
| `PAPS` | ` IEC_EchoPaSyst` |  |   |
| `PAPS_V` | ` IEC_EchoPaSyst` |  |   |
| `PAPS_CLASSE` | ` Transcoding based on IEC_EchoPaSyst` |  |   |
| `DEGURG` | ` int_urgence` |  |   |
| `COMINT` | ` Complex transcoding` |  |   |
| `CHIRAO` | ` igs_chiaort` |  |   |
| `MARFAN` | ` Transcoding based on IDG_Etio_Marfan` |  |   |
| `CIVPI` | ` Transcoding based on igs_chi_fermeture_civa` |  |   |
| `NOMB_VCPA` | ` Transcoding involving multiple columns` |  |   |
| `STEN` | ` Transcoding based on iec_corog_degre` |  |   |
| `ANTANC` | ` Transcoding based on ian_dateptca1,2,3,4` |  |   |
| `INSAOR` | ` Transcoding involving multiple columns` |  |   |
| `ETIOAMTP_C1` | ` Transcoding involving multiple columns` |  |   |
| `ETIOAMTP_C2` | ` Transcoding involving multiple columns` |  |   |
| `ETIOAMTP_C3` | ` Transcoding involving multiple columns` |  |   |
| `ETIOAMTP_C4` | ` Transcoding involving multiple columns` |  |   |
| `RETAOR` | ` decode(idg_lesionvalv_ra,NULL,0,1)` |  |   |
| `RETMIT` | ` decode(idg_lesionvalv_rm,NULL,0,1)` |  |   |
| `RETTRI` | ` decode(idg_lesionvalv_rt,NULL,0,1)` |  |   |
| `RETPULM` | ` decode(idg_lesionvalv_rp,NULL,0,1)` |  |   |
| `HTA` | ` One-to-one of ipo_risq_hta` |  |   |
| `HCHOL` | ` One-to-one of IPO_Risq_Dyslip` |  |   |
| `TAVK` | ` Transcoding of ipo_patho_anticoag` |  |   |
| `TAA` | ` Transcoding of ipo_patho_antiag` |  |   |
| `DOURAA` | ` Coded as missing (2)` |  |   |
| `NINCEC` | ` Transcoding` |  |   |
| `ATCDF` | ` NULL` |  |   |
| `DOSSIER` | ` NULL` |  |   |
| `COMPAT` | ` NULL` |  |   |
| `CHIRAV      /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `CHIRAV_V    /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `INTMCEC     /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `INTMCEC_V   /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `EUROSCORE1  /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `EUROSCORE1_V/* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `EUROSCOREL  /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `EUROSCOREL_V/* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `CPBIA_PEROP /* Obsolete data EPICARD.v1 */` | ` NULL` |  |   |
| `DATINT_D` | ` to_char(INT_DATEINTERVENTION,'DD')` |  |   |
| `DATINT_M` | ` to_char(INT_DATEINTERVENTION,'MM')` |  |   |
| `DATINT_Y` | ` to_char(INT_DATEINTERVENTION,'YYYY')` |  |   |
| `DATINT` | ` to_char(INT_DATEINTERVENTION,'DD/MM/YYYY')` |  |   |
| `CODCHIR1` | ` Transcoding of 1st surgeon's first and last names` |  |   |
| `NBRPPS1` | ` Transcoding of 1st surgeon's RPPS` |  |   |
| `CODCHIR2` | ` Transcoding of 2nd surgeon's first and last name` |  |   |
| `NBRPPS2` | ` Transcoding of 2nd surgeon's RPPS` |  |   |
| `TYPECHIR_C1` | ` One-to-one of DECODE(igs_chicor, NULL, NULL, 1)` |  |   |
| `TYPECHIR_C2` | ` Transcoding` |  |   |
| `TYPECHIR_C3` | ` One-to-one: DECODE(IGS_CHIAORT, NULL, NULL, 1)` |  |   |
| `DURCLAMP` | ` One-to-one based on int_tpsclamp` |  |   |
| `DURCLAMP_V` | ` One-to-one based on  int_tpsclamp` |  |   |
| `DURCEC` | ` One-to-one based on int_tpscec` |  |   |
| `DURCEC_V` | ` One-to-one based on int_tpscec` |  |   |
| `PROTCER` | ` Transcoding` |  |   |
| `GVA` | ` Simple transcoding` |  |   |
| `PROTCERA_C1` | ` Simple transcoding of INT_PERFCEREB` |  |   |
| `PROTCERA_C2` | ` Simple transcoding of int_itgarretcirc` |  |   |
| `PROTCERA_C3` | ` Simple transcoding of INT_PERFCEREB` |  |   |
| `VOIESAB_C1` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C2` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C3` | ` Simple transcoding of IGS_CHIENDO` |  |   |
| `VOIESAB_C4` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C5` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C6` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C7` | ` Simple transcoding of INT_Voie` |  |   |
| `VOIESAB_C8` | ` NULL` |  |   |
| `VOIESAB_C9` | ` NULL` |  |   |
| `VOIESAB_C11` | ` NULL` |  |   |
| `VOIESAB_C10` | ` Simple transcoding of INT_Voie` |  |   |
| `SIVOIES_1` | ` Transcoding` |  |   |
| `SIVOIES_2` | ` Transcoding` |  |   |
| `SIVOIES_3` | ` Transcoding` |  |   |
| `NTHCENTRE` | ` NULL` |  |   |
| `NTCA` | ` Transcoding` |  |   |
| `NTCA_V` | ` Transcoding (copied)` |  |   |
| `NACCA` | ` Transcoding` |  |   |
| `NACCA_V` | ` Transcoding (copied)` |  |   |
| `NTCV` | ` Transcoding` |  |   |
| `NTCV_V` | ` Transcoding` |  |   |
| `NACCV` | ` Transcoding` |  |   |
| `NACCV_V` | ` Transcoding` |  |   |
| `CTAIRECORO` | ` ''` |  |   |
| `GESTEV_C1` | ` Transcoding` |  |   |
| `GESTEV_C2` | ` Transcoding` |  |   |
| `GESTEV_C3` | ` Transcoding` |  |   |
| `GESTEV_C4` | ` Transcoding` |  |   |
| `CVAO` | ` Transcoding` |  |   |
| `AORVALO` | ` Transcoding` |  |   |
| `NUMSERA` | ` One to one of IGS_ChiValvaire_RVANSerie` |  |   |
| `NUMLOTA` | ` NULL` |  |   |
| `GVMO` | ` Transcoding` |  |   |
| `FABRICANTM` | ` Transcoding` |  |   |
| `MODELEM` | ` Transcoding` |  |   |
| `TAILLEM` | ` Transcoding` |  |   |
| `NUMSERM` | ` One to one of IGS_ChiValvaire_RVMNSerie` |  |   |
| `NUMLOTM` | ` NULL` |  |   |
| `GVTO` | ` Transcoding` |  |   |
| `TRIVALO` | ` Transcoding based on IGS_ChiValvaire_RVTType` |  |   |
| `FABRICANTT` | ` Transcoding based on` |  |   |
| `MODELET` | ` Transcoding based on IGS_ChiValvaire_RVTType` |  |   |
| `TAILLET` | ` Transcoding based on IGS_ChiValvaire_RVTType and   IGS_ChiValvaire_RVTTaille` |  |   |
| `NUMSERT` | ` One-to-one of IGS_ChiValvaire_RVTNSerie` |  |   |
| `NUMLOTT` | ` NULL` |  |   |
| `GVPO` | ` Transcoding based on IGS_ChiValvaire_RVPType` |  |   |
| `PULMVALO` | ` Transcoding based on IGS_ChiValvaire_RVPType` |  |   |
| `FABRICANTP` | ` Transcoding based on IGS_ChiValvaire_RVPType` |  |   |
| `MODELEP` | ` Transcoding based on IGS_ChiValvaire_RVPType` |  |   |
| `TAILLEP` | ` Transcoding based on IGS_ChiValvaire_RVPType and IGS_ChiValvaire_RVPTaille` |  |   |
| `NUMSERP` | ` One-to-one of IGS_ChiValvaire_RVPNSerie` |  |   |
| `NUMLOTP` | ` NULL` |  |   |
| `CTAIREVALV` | ` NULL` |  |   |
| `DIAGO` | ` Transcoding` |  |   |
| `GESTEO` | ` Transcoding` |  |   |
| `LOCO_C1` | ` One-to-one transcoding of IGS_ChiAort_AS` |  |   |
| `LOCO_C2` | ` One-to-one transcoding of IGS_ChiAort_AS` |  |   |
| `LOCO_C3` | ` One-to-one transcoding of IGS_ChiAort_Crosse` |  |   |
| `LOCO_C4` | ` Simple transcoding of IDG_RuptAO and IGS_ChiAort` |  |   |
| `LOCO_C5` | ` One-to-one transcoding of IGS_ChiAort_DE` |  |   |
| `LOCO_C6` | ` NULL` |  |   |
| `STENT` | ` One-to-one transcoding of IGS_ChiAort_DE` |  |   |
| `STENTO` | ` One-to-one transcoding of IGS_ChiAort_Crosse` |  |   |
| `NB_TUBE` | ` NULL` |  |   |
| `FABRICANTCA1` | ` NULL` |  |   |
| `MODELECA1` | ` NULL` |  |   |
| `TAILLECA1` | ` NULL` |  |   |
| `NUMSERCA1` | ` NULL` |  |   |
| `NUMLOTCA1` | ` NULL` |  |   |
| `FABRICANTCA2` | ` NULL` |  |   |
| `MODELECA2` | ` NULL` |  |   |
| `TAILLECA2` | ` NULL` |  |   |
| `NUMSERCA2` | ` NULL` |  |   |
| `NUMLOTCA2` | ` NULL` |  |   |
| `FABRICANTCA3` | ` NULL` |  |   |
| `MODELECA3` | ` NULL` |  |   |
| `TAILLECA3` | ` NULL` |  |   |
| `NUMSERCA3` | ` NULL` |  |   |
| `NUMLOTCA3` | ` NULL` |  |   |
| `PROTVO` | ` Transcoding` |  |   |
| `PROTAOTYPE` | ` Transcoding` |  |   |
| `TAILLECA4` | ` Transcoding of IGS_ChiAort` |  |   |
| `NUMSERCA4` | ` Transcoding of IGS_ChiAort` |  |   |
| `NUMLOTCA4` | ` NULL` |  |   |
| `COMM` | ` NULL` |  |   |
| `CHIRDIV_C1` | ` One-to-one transcoding of igs_chi_fermeture_civa` |  |   |
| `CHIRDIV_C2` | ` One-to-one transcoding of igs_chi_fermeture_civp` |  |   |
| `CHIRDIV_C3` | ` One-to-one transcoding of igs_chiaut_cmo` |  |   |
| `CHIRDIV_C4` | ` One-to-one transcoding of igs_chi_resanevrisme` |  |   |
| `CHIRDIV_C5` | ` One-to-one transcoding of igs_chi_complication_rupt` |  |   |
| `CHIRDIV_C6` | ` Simple transcoding based on INT_BasCgx and AGE_CALCUL` |  |   |
| `CHIRDIV_C7` | ` One-to-one transcoding of igs_chiaut_emboliepulm` |  |   |
| `CHIRDIV_C8` | ` One-to-one transcoding of igs_chi_complication_rythme` |  |   |
| `CHIRDIV_C9` | ` One-to-one transcoding of igs_chiaut_tum` |  |   |
| `CHIRDIV_C10` | ` One-to-one transcoding of idg_coeurcontusion` |  |   |
| `CHIRDIV_C11` | ` One-to-one transcoding of idg_coeurplaie` |  |   |
| `CHIRDIV_C12` | ` NULL` |  |   |
| `CHIRDIV_C13` | ` One-to-one transcoding of igs_chiaut_gref` |  |   |
| `CHIRDIV_C14` | ` NULL` |  |   |
| `CHIRDIV_C15` | ` NULL` |  |   |
| `CHIRDIV_C16` | ` NULL` |  |   |
| `CHIRDIV_C17` | ` NULL` |  |   |
| `CHIRDIV_C18` | ` One-to-one transcoding of IGS_CHIAUT_DEFIBRILL` |  |   |
| `CHIRDIV_C19` | ` Transcoding` |  |   |
| `AUTRCHIT` | ` NULL` |  |   |
| `AUTRCHIRCVO_C1` | ` One-to-one transcoding of IGS_CHIAUT_ASSOC` |  |   |
| `AUTRCHIRCVO_C2` | ` NULL` |  |   |
| `AUTRCHIRNCTO_C1` | ` NULL` |  |   |
| `AUTRCHIRNCTO_C2` | ` One-to-one transcoding of IGS_CHIAUT_ASSOC` |  |   |
| `DRECMOIS_C1` | ` NULL` |  |   |
| `DRECMOIS_C2` | ` NULL` |  |   |
| `DRECMOIS_C3` | ` One-to-one transcoding of IGS_CHIAUT_LONGDUREE` |  |   |
| `TRANS` | ` Transcoding` |  |   |
| `GRAVGLOB` | ` NULL` |  |   |
| `REINTERV` | ` Transcoding` |  |   |
| `REINTCECO` | ` Transcoding of iso_REINT` |  |   |
| `COMPLL_C1` | ` One-to-one transcoding of ISO_Saignt` |  |   |
| `COMPLL_C2` | ` One-to-one transcoding of iso_reprisetamp` |  |   |
| `COMPLL_C3` | ` One-to-one transcoding of ISO_DOBU` |  |   |
| `COMPLL_C4` | ` Transcoding` |  |   |
| `COMPLL_C5` | ` Transcoding` |  |   |
| `COMPLL_C6` | ` Transcoding` |  |   |
| `COMPLL_C7` | ` One-to-one ISO_ECGRythme` |  |   |
| `COMPLL_C8` | ` One-to-one iso_insrenale` |  |   |
| `COMPLL_C9` | ` One-to-one iso_ventilprolonge` |  |   |
| `COMPLL_C10` | ` NULL` |  |   |
| `COMPLL_C30` | ` NULL` |  |   |
| `COMPLL_C11` | ` One-to-one ISO_Desunion` |  |   |
| `COMPLL_C12` | ` One-to-one iso_sepsimedia` |  |   |
| `COMPLL_C13` | ` NULL` |  |   |
| `COMPLL_C14` | ` One-to-one ISO_ECHOSurfA and ISO_ECHOSurfM` |  |   |
| `COMPLL_C15` | ` One-to-one ISO_CPProthese_DYS` |  |   |
| `COMPLL_C16` | ` One-to-one iso_hemorragiedigest` |  |   |
| `COMPLL_C17` | ` NULL` |  |   |
| `COMPLL_C18` | ` One-to-one iso_cpneuro_avc = 1` |  |   |
| `COMPLL_C19` | ` One-to-one iso_cpneuro_avc = 2` |  |   |
| `COMPLL_C20` | ` One-to-one iso_cpneuro_coma` |  |   |
| `COMPLL_C21` | ` One-to-one ISO_ECGRythme` |  |   |
| `COMPLL_C22` | ` One-to-one ISO_ECGCond_BAV` |  |   |
| `COMPLL_C23` | ` One-to-one iso_cond_pace` |  |   |
| `COMPLL_C24` | ` NULL` |  |   |
| `COMPLL_C25` | ` ISO_AccidentHemo` |  |   |
| `COMPLL_C26` | ` ISO_AllHeparine` |  |   |
| `COMPLL_C27` | ` NULL` |  |   |
| `COMPLL_C28` | ` NULL` |  |   |
| `COMPLL_C29` | ` NULL` |  |   |
| `AUTRCOMT` | ` NULL` |  |   |
| `DATESORT_D` | ` to_char(INT_DateSortie,'DD')` |  |   |
| `DATESORT_M` | ` to_char(INT_DateSortie,'MM')` |  |   |
| `DATESORT_Y` | ` to_char(INT_DateSortie,'YYYY')` |  |   |
| `DATESORT` | ` to_char(INT_DateSortie,'DD/MM/YYYY')` |  |   |
| `STAT` | ` decode(PAT_DCD,NULL,0,1)` |  |   |
| `DEC30J` | ` One-to-one calculated` |  |   |
| `DATEDEC_D` | ` to_char(pat_datedeces,'DD')` |  |   |
| `DATEDEC_M` | ` to_char(pat_datedeces,'MM')` |  |   |
| `DATEDEC_Y` | ` to_char(pat_datedeces,'YYYY')` |  |   |
| `DATEDEC` | ` to_char(pat_datedeces,'DD/MM/YYYY')` |  |   |
| `DELDEC` | ` Simple transcoding` |  |   |
| `DELDEC_V` | ` Simple transcoding (copied)` |  |   |
| `CAUSEDEATH` | ` Transcoding for death etiology` |  |   |
| `CTAIREDECE` | ` NULL` |  |   |
| `EILS_TITTRE1` | ` NULL` |  |   |
| `EILS_TITTRE_L1` | ` NULL` |  |   |
| `TITRE_EILS_AUTT_L1` | ` NULL` |  |   |
| `RISQ_EILST_L1` | ` NULL` |  |   |
| `AUTRRISQT_L1` | ` NULL` |  |   |
| `DEFAILLANCE_EILST_L1` | ` NULL` |  |   |
| `MOMENT_EILST_L1` | ` NULL` |  |   |
| `EILS_DESCRT_L1` | ` NULL` |  |   |
| `DATEDN_F1_D` | ` NULL` |  |   |
| `DATEDN_F1_M` | ` NULL` |  |   |
| `DATEDN_F1_Y` | ` NULL` |  |   |
| `DATEDN_F1` | ` NULL` |  |   |
| `TYPECONSULTACTE_F1` | ` NULL` |  |   |
| `STATUT_F1` | ` NULL` |  |   |
| `RCP_F1` | ` NULL` |  |   |
| `TRT_FAIT_F1` | ` NULL` |  |   |
| `PROTOC_YN_F1` | ` NULL` |  |   |
| `COMMENT_DN_F1` | ` NULL` |  |   |
| `DECAPRESSORT` | ` Simple transcoding` |  |   |
| `OCOMPL` | ` Transcoding` |  |   |
| `CLEARDIAL_CLASSE` | ` Transcoding` |  |   |
| `ETIOA` | ` Transcoding` |  |   |
| `INSMIT` | ` Transcoding` |  |   |
| `ETIOM` | ` Transcoding` |  |   |
| `INSTRI` | ` Transcoding` |  |   |
| `ETIOT` | ` Complex transcoding` |  |   |
| `INSPULM` | ` Complex transcoding` |  |   |
| `ETIOP` | ` Transcoding` |  |   |
| `TYPECHIR_C4` | ` Transcoding` |  |   |
| `CEC` | ` One-to-one and transcoding int_coeurbattant` |  |   |
| `FABRICANTA` | ` Transcoding based on IGS_ChiValvaire_RVAType` |  |   |
| `MODELEA` | ` Transcoding based on IGS_ChiValvaire_RVAType` |  |   |
| `TAILLEA` | ` Transcoding based on IGS_ChiValvaire_RVAType and Taille` |  |   |
| `MITVALO` | ` Trasncoding based on RVMType` |  |   |
| `FABRICANTCA4` | ` Transcoding based on IGS_ChiValvaire_RVAType` |  |   |
| `MODLECA4` | ` Transcoding based on IGS_ChiValvaire_RVAType` |  |   |
| `NTAC` | ` One-to-one NTCV_V+NACCV_V` |  |   |
| `NTAC_V` | ` One-to-one NTCV_V+NACCV_V` |  |   |

## Exclusion criteria <a name="exclusion-criteria"></a>
1. No endoprostheses (IGS_CHIENDO)
2. No re-operated patient (redux)
3. No followed-up patients (returns only the first intervention row_number == 1)
4. No incoherent weight (>250)
