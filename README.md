------------------------------------------------------------------------

## Description

Provides details such as Morphine Equivalent Dose (MED), brand name and
opioid content which are calculated of all oral opioids authorized for
sale by Health Canada based on their Drug Identification Number (DIN)
or FDA based on their Product ID for Opioids authorized for sale in
Canadian or US markets.
For US Opioids, MEDs are calculated using Von Korff et al. (2008) and information
obtained from FDA's daily National Drug Code Directory [/drug/ndc] download
MEDs are calculated based on recommendations by Canadian Institute for
Health Information (CIHI) and information obtained from Health Canada’s
Drug Product Database’s monthly data dump for Canadian Opioids. 
Please note in no way should
output from this package be a substitute for medical advise.  
All medications should only be consumed on prescription from a licensed
healthcare provider

------------------------------------------------------------------------

US_table <- load_Opioid_Table(country="US")
The FDA_Opioid_Table is up to date.
DISCLAIMER: Not a substitute for medical advise. Please note that the output generated by the package should not be substituted for clinical advise and any medication should be only consumed at the advise of a licensed healthcare provider.

Source url of the data: https://download.open.fda.gov/drug/ndc/drug-ndc-0001-of-0001.json.zip
Source url used for dosing: Von Korff M, Saunders K, Thomas Ray G, et al. De facto long-term opioid therapy for noncancer pain. Clin J Pain 2008; 24: 521-527. 2008/06/25. DOI: 10.1097/AJP.0b013e318169d03b.
> head(US_table)
    Drug_ID                             name strength Base1 Base2 Base3
1 0054-0176      BUPRENORPHINE HYDROCHLORIDE   2 mg/1   2.0     1      
2 0054-0177      BUPRENORPHINE HYDROCHLORIDE   8 mg/1   8.0     1      
3 0054-0188      BUPRENORPHINE HYDROCHLORIDE   2 mg/1   2.0     1      
4 0054-0188 NALOXONE HYDROCHLORIDE DIHYDRATE  .5 mg/1   0.5     1      
5 0054-0189      BUPRENORPHINE HYDROCHLORIDE   8 mg/1   8.0     1      
6 0054-0189 NALOXONE HYDROCHLORIDE DIHYDRATE   2 mg/1   2.0     1      
                                                             Brand
1                                                Buprenorphine HCl
2                                                Buprenorphine HCl
3 buprenorphine hydrochloride and naloxone hydrochloride dihydrate
4 buprenorphine hydrochloride and naloxone hydrochloride dihydrate
5 buprenorphine hydrochloride and naloxone hydrochloride dihydrate
6 buprenorphine hydrochloride and naloxone hydrochloride dihydrate
                                                              active_ingredients marketing_category   Form      Route
1                                            BUPRENORPHINE HYDROCHLORIDE, 2 mg/1               ANDA TABLET SUBLINGUAL
2                                            BUPRENORPHINE HYDROCHLORIDE, 8 mg/1               ANDA TABLET SUBLINGUAL
3 BUPRENORPHINE HYDROCHLORIDE, NALOXONE HYDROCHLORIDE DIHYDRATE, 2 mg/1, .5 mg/1               ANDA TABLET SUBLINGUAL
4 BUPRENORPHINE HYDROCHLORIDE, NALOXONE HYDROCHLORIDE DIHYDRATE, 2 mg/1, .5 mg/1               ANDA TABLET SUBLINGUAL
5  BUPRENORPHINE HYDROCHLORIDE, NALOXONE HYDROCHLORIDE DIHYDRATE, 8 mg/1, 2 mg/1               ANDA TABLET SUBLINGUAL
6  BUPRENORPHINE HYDROCHLORIDE, NALOXONE HYDROCHLORIDE DIHYDRATE, 8 mg/1, 2 mg/1               ANDA TABLET SUBLINGUAL
                                                                            Opioid      Opioid_1 MED_per_dispensing_unit
1                                             BUPRENORPHINE HYDROCHLORIDE 2 mg/1   BUPRENORPHINE                      NA
2                                             BUPRENORPHINE HYDROCHLORIDE 8 mg/1   BUPRENORPHINE                      NA
3 BUPRENORPHINE HYDROCHLORIDE 2 mg/1  + NALOXONE HYDROCHLORIDE DIHYDRATE .5 mg/1   BUPRENORPHINE                      NA
4 BUPRENORPHINE HYDROCHLORIDE 2 mg/1  + NALOXONE HYDROCHLORIDE DIHYDRATE .5 mg/1        NALOXONE                      NA
5  BUPRENORPHINE HYDROCHLORIDE 8 mg/1  + NALOXONE HYDROCHLORIDE DIHYDRATE 2 mg/1   BUPRENORPHINE                      NA
6  BUPRENORPHINE HYDROCHLORIDE 8 mg/1  + NALOXONE HYDROCHLORIDE DIHYDRATE 2 mg/1        NALOXONE                      NA
  No_tabs/ml.assuming.50.MED.limit.per.day No_tabs/ml.assuming.90.MED.limit.per.day
1                                       NA                                       NA
2                                       NA                                       NA
3                                       NA                                       NA
4                                       NA                                       NA
5                                       NA                                       NA
6                                       NA                                       NA
  Maximum.No_tabs/ml.assuming.50.MED.limit.for.7.days Maximum.No_tabs/ml.assuming.50.MED.limit.for.14.days
1                                                  NA                                                   NA
2                                                  NA                                                   NA
3                                                  NA                                                   NA
4                                                  NA                                                   NA
5                                                  NA                                                   NA
6                                                  NA                                                   NA
  Maximum.No_tabs/ml.assuming.50.MED.limit.for.30.days last_updated
1                                                   NA        45277
2                                                   NA        45277
3                                                   NA        45277
4                                                   NA        45277
5                                                   NA        45277
6                                                   NA        45277

############################################################################################################################################
Canada_table <- load_opioid_data("Canada")
The HealthCanada_Opioid_Table is up to date.
DISCLAIMER: Not a substitute for medical advise. Please note that the output generated by the package should not be substituted for clinical advise and any medication should be only consumed at the advise of a licensed healthcare provider.

Source url of the data: https://www.canada.ca/en/health-canada/services/drugs-health-products/drug-products/drug-product-database/what-data-extract-drug-product-database.html
Source url used for dosing: https://www.cihi.ca/sites/default/files/document/opioid-prescribing-canada-trends-en-web.pdf
> head(Canada_table)
  Drug_ID MED_per_dispensing_unit Base1 Base2 Base3             Opioid      Route   Form                       Brand
1 2517175  Couldn't be calculated     1     N       BUPRENORPHINE 2 MG SUBLINGUAL TABLET TARO-BUPRENORPHINE/NALOXONE
2 2517175  Couldn't be calculated     1     N          NALOXONE 0.5 MG SUBLINGUAL TABLET TARO-BUPRENORPHINE/NALOXONE
3 2517183  Couldn't be calculated     1     N       BUPRENORPHINE 8 MG SUBLINGUAL TABLET TARO-BUPRENORPHINE/NALOXONE
4 2517183  Couldn't be calculated     1     N            NALOXONE 2 MG SUBLINGUAL TABLET TARO-BUPRENORPHINE/NALOXONE
5 2518759                       5     1     N           TRAMADOL 50 MG       ORAL TABLET           JAMP TRAMADOL HCL
6  763527                     1.2     1     N             CODEINE 8 MG       ORAL TABLET            ORADRINE TABLETS
  No_tabs/ml.assuming.50.MED.limit.per.day No_tabs/ml.assuming.90.MED.limit.per.day
1                   Couldn't be calculated                   Couldn't be calculated
2                   Couldn't be calculated                   Couldn't be calculated
3                   Couldn't be calculated                   Couldn't be calculated
4                   Couldn't be calculated                   Couldn't be calculated
5                                       10                                       18
6                                       42                                       75
  Maximum.No_tabs/ml.assuming.50.MED.limit.for.7.days Maximum.No_tabs/ml.assuming.50.MED.limit.for.14.days
1                              Couldn't be calculated                               Couldn't be calculated
2                              Couldn't be calculated                               Couldn't be calculated
3                              Couldn't be calculated                               Couldn't be calculated
4                              Couldn't be calculated                               Couldn't be calculated
5                                                  70                                                  140
6                                                 294                                                  588
  Maximum.No_tabs/ml.assuming.50.MED.limit.for.30.days              Status_1 last_updated
1                               Couldn't be calculated              APPROVED        45261
2                               Couldn't be calculated              APPROVED        45261
3                               Couldn't be calculated              APPROVED        45261
4                               Couldn't be calculated              APPROVED        45261
5                                                  300              MARKETED        45261
6                                                 1260 CANCELLED POST MARKET        45261

############################################################
MED("0093-0058", US_Table)
[1] 5

MED(786535, Canada_Table)
[1] 5

############################################################
Opioid("0093-0058", US_Table)
[1] "TRAMADOL HYDROCHLORIDE 50 mg/1  "
Opioid(786535, Canada_Table)
[1] "HYDROMORPHONE 1 MG"

############################################################
Brand("0093-0058", US_Table)
[1] "Tramadol Hydrochloride"
Brand(786535, Canada_Table)
[1] "DILAUDID"

############################################################
MED_50("0093-0058", US_Table)
[1] 10
MED_50(786535, Canada_Table)
[1] 10
############################################################
MED_90("0093-0058", US_Table)
[1] 18
MED_90(786535, Canada_Table)
[1] 18
