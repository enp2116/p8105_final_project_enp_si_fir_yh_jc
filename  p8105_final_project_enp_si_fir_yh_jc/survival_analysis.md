Survival Analysis
================
2022-11-26

## Survival Analysis

#### Create new variable ethnicity

#### Create time and status variable

## Survival Unadjected Model

<img src="/Users/bk22/Documents/Graduate_School/2022_2_Fall/Data_Science_I/p8105_final_project_enp_si_fir_yh_jc/ p8105_final_project_enp_si_fir_yh_jc/survival_analysis_files/figure-gfm/unnamed-chunk-5-1.png" data-figure-id=fig1 />

## Cox-proposional hazard model 1

    Call:
    coxph(formula = Surv(time, status) ~ poc + age_during_show + 
        personality_type_binary, data = survivor_final)

      n= 721, number of events= 626 
       (15 observations deleted due to missingness)

                                           coef  exp(coef)   se(coef)      z
    pocWhite                         -1.186e-01  8.881e-01  8.923e-02 -1.330
    age_during_show                  -8.572e-06  1.000e+00  3.976e-03 -0.002
    personality_type_binaryIntrovert  6.114e-02  1.063e+00  8.065e-02  0.758
                                     Pr(>|z|)
    pocWhite                            0.184
    age_during_show                     0.998
    personality_type_binaryIntrovert    0.448

                                     exp(coef) exp(-coef) lower .95 upper .95
    pocWhite                            0.8881     1.1260    0.7456     1.058
    age_during_show                     1.0000     1.0000    0.9922     1.008
    personality_type_binaryIntrovert    1.0631     0.9407    0.9076     1.245

    Concordance= 0.517  (se = 0.014 )
    Likelihood ratio test= 2.47  on 3 df,   p=0.5
    Wald test            = 2.5  on 3 df,   p=0.5
    Score (logrank) test = 2.51  on 3 df,   p=0.5

## Cox-proposional hazard model 2

    Call:
    coxph(formula = Surv(time, status) ~ ethnicity + age_during_show + 
        personality_type_binary, data = survivor_final)

      n= 687, number of events= 596 
       (49 observations deleted due to missingness)

                                           coef  exp(coef)   se(coef)      z
    ethnicityAsian, Black             3.2903748 26.8529253  1.0259043  3.207
    ethnicityBlack                   -0.0013271  0.9986737  0.1847155 -0.007
    ethnicityBrazilian               -0.2720196  0.7618393  0.7249443 -0.375
    ethnicityChilean American         1.7268978  5.6231827  1.0168787  1.698
    ethnicityColombian American      -0.1342845  0.8743413  1.0129903 -0.133
    ethnicityCuban American          -0.3704447  0.6904272  1.0113371 -0.366
    ethnicityMexican American        -0.1970779  0.8211267  0.4350155 -0.453
    ethnicityPanamanian American      3.3588111 28.7549837  1.0278275  3.268
    ethnicityPeruvian American        1.8464144  6.3370565  1.0154234  1.818
    ethnicityPuerto Rican American   -0.2202243  0.8023388  0.7223740 -0.305
    ethnicityVenezuelan American      1.1023898  3.0113541  1.0129948  1.088
    ethnicityWhite                   -0.1095644  0.8962244  0.1552187 -0.706
    age_during_show                   0.0002771  1.0002771  0.0040463  0.068
    personality_type_binaryIntrovert  0.0656655  1.0678694  0.0845104  0.777
                                     Pr(>|z|)   
    ethnicityAsian, Black             0.00134 **
    ethnicityBlack                    0.99427   
    ethnicityBrazilian                0.70749   
    ethnicityChilean American         0.08946 . 
    ethnicityColombian American       0.89454   
    ethnicityCuban American           0.71415   
    ethnicityMexican American         0.65052   
    ethnicityPanamanian American      0.00108 **
    ethnicityPeruvian American        0.06901 . 
    ethnicityPuerto Rican American    0.76047   
    ethnicityVenezuelan American      0.27649   
    ethnicityWhite                    0.48027   
    age_during_show                   0.94540   
    personality_type_binaryIntrovert  0.43715   
    ---
    Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

                                     exp(coef) exp(-coef) lower .95 upper .95
    ethnicityAsian, Black              26.8529    0.03724   3.59534   200.559
    ethnicityBlack                      0.9987    1.00133   0.69533     1.434
    ethnicityBrazilian                  0.7618    1.31261   0.18399     3.155
    ethnicityChilean American           5.6232    0.17784   0.76633    41.262
    ethnicityColombian American         0.8743    1.14372   0.12007     6.367
    ethnicityCuban American             0.6904    1.44838   0.09512     5.012
    ethnicityMexican American           0.8211    1.21784   0.35005     1.926
    ethnicityPanamanian American       28.7550    0.03478   3.83552   215.577
    ethnicityPeruvian American          6.3371    0.15780   0.86608    46.368
    ethnicityPuerto Rican American      0.8023    1.24636   0.19475     3.306
    ethnicityVenezuelan American        3.0114    0.33208   0.41352    21.929
    ethnicityWhite                      0.8962    1.11579   0.66114     1.215
    age_during_show                     1.0003    0.99972   0.99238     1.008
    personality_type_binaryIntrovert    1.0679    0.93644   0.90486     1.260

    Concordance= 0.532  (se = 0.013 )
    Likelihood ratio test= 16.88  on 14 df,   p=0.3
    Wald test            = 31.88  on 14 df,   p=0.004
    Score (logrank) test = 65.12  on 14 df,   p=1e-08

## Kaplan-Meier plotter-personality

<img src="/Users/bk22/Documents/Graduate_School/2022_2_Fall/Data_Science_I/p8105_final_project_enp_si_fir_yh_jc/ p8105_final_project_enp_si_fir_yh_jc/survival_analysis_files/figure-gfm/unnamed-chunk-8-1.png" data-figure-id=fig2 />

## Kaplan-Meier plotter-White vs Non-White

<img src="/Users/bk22/Documents/Graduate_School/2022_2_Fall/Data_Science_I/p8105_final_project_enp_si_fir_yh_jc/ p8105_final_project_enp_si_fir_yh_jc/survival_analysis_files/figure-gfm/unnamed-chunk-9-1.png" data-figure-id=fig3 />

## Kaplan-Meier plotter-gender

<img src="/Users/bk22/Documents/Graduate_School/2022_2_Fall/Data_Science_I/p8105_final_project_enp_si_fir_yh_jc/ p8105_final_project_enp_si_fir_yh_jc/survival_analysis_files/figure-gfm/unnamed-chunk-10-1.png" data-figure-id=fig4 />

## log-rank
