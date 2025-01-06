=========
rvpix_exp
=========

:Summary: RVSpecfit measurements from individual exposures in different
     surveys, programs.
:Naming Convention: ``rvpix_exp-{SURVEY}-{PROGRAM}.fits``, where survey is sv1,
     sv2.. program is dark, bright, ... 
:File Type: FITS, 5 GB  *This section gives the type of the file
    and its approximate size.*

Contents
========

====== ======== ======== ====================================================
Number EXTNAME  Type     Contents
====== ======== ======== ====================================================
HDU0_           IMAGE    Empty HDU
HDU1_  RVTAB    BINTABLE RVSpecfit results
HDU2_  FIBERMAP BINTABLE Information about objects inherited from targeting
HDU3_  SCORES   BINTABLE Information about spectra quality
HDU4_  GAIA     BINTABLE Gaia crossmatch
====== ======== ======== ====================================================


FITS Header Units
=================

HDU0
----

*Summarize the contents of this HDU.*

This HDU has no non-standard required keywords.

Empty HDU.

HDU1
----

EXTNAME = RVTAB

This is table of measurements by RVSpecfit of individual exposures in DESI for
a given survey/program.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   265              int  length of dimension 1
    NAXIS2   3572976          int  length of dimension 2
    CHECKSUM BahGCUf9BafEBUf9 str  HDU checksum updated 2024-12-19T17:16:48
    DATASUM  1913037089       str  data unit checksum updated 2024-12-19T17:16:48
    ======== ================ ==== ==============================================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

=========== ======= ====== =======================================================================================================================================
Name        Type    Units  Description
=========== ======= ====== =======================================================================================================================================
VRAD        float64 km s-1 Radial velocity
VRAD_ERR    float64 km s-1 Radial velocity error
VRAD_SKEW   float64        Radial velocity posterior skewness
VRAD_KURT   float64        Radial velocity posterior kurtosis
LOGG        float64        Log of surface gravity
TEFF        float64 K      Effective temperature
ALPHAFE     float64        [alpha/Fe] from template fitting
FEH         float64        [Fe/H] from template fitting
LOGG_ERR    float64        Log of surface gravity uncertainty
TEFF_ERR    float64 K      Effective temperature uncertainty
ALPHAFE_ERR float64        [alpha/Fe] uncertainty from template fitting
FEH_ERR     float64        [Fe/H] uncertainty from template fitting
VSINI       float64 km s-1 Stellar rotation velocity
CHISQ_TOT   float64        Total chi-square for all arms
CHISQ_C_TOT float64        Total chi-square for all arms for polynomial only fit
CHISQ_B     float64        Chi-square in the B arm
CHISQ_C_B   float64        Chi-square in the B arm after fitting continuum only
CHISQ_R     float64        Chi-square in the R arm
CHISQ_C_R   float64        Chi-square in the R arm after fitting continuum only
CHISQ_Z     float64        Chi-square in the Z arm
CHISQ_C_Z   float64        Chi-square in the Z arm after fitting continuum only
RVS_WARN    int64          RVSpecFit warning flag
FIBER       int32          Fiber ID on the CCDs [0-4999]
REF_ID      int64          Tyc1*1,000,000+Tyc2*10+Tyc3 for Tycho-2; ``sourceid`` for Gaia DR2
REF_CAT     char[2]        Reference catalog source for star: &#x27;T2&#x27; for Tycho-2, &#x27;G2&#x27; for Gaia DR2, &#x27;L2&#x27; for the SGA, empty otherwise
TARGET_RA   float64 deg    Barycentric right ascension in ICRS
TARGET_DEC  float64 deg    Barycentric declination in ICRS
TARGETID    int64          Unique DESI target ID
EXPID       int32          DESI Exposure ID number
SN_B        float64        Median S/N in the B arm
SN_R        float64        Median S/N in the R arm
SN_Z        float64        Median S/N in the Z arm
SUCCESS     logical        Did we succeed or fail
RR_Z        float64        Redrock redshift
RR_SPECTYPE char[6]        Redrock spectype
HEALPIX     int64          HEALPixel containing this location at NSIDE=64 in the NESTED scheme
=========== ======= ====== =======================================================================================================================================

HDU2
----

EXTNAME = FIBERMAP

FIBERMAP table with information on individual targets copied from original spectra- file.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   389              int  length of dimension 1
    NAXIS2   3572976          int  length of dimension 2
    CHECKSUM 2CZO39WL2AWL29WL str  HDU checksum updated 2024-12-19T17:17:17
    DATASUM  495390822        str  data unit checksum updated 2024-12-19T17:17:17
    ======== ================ ==== ==============================================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

===================== ======= ============ =======================================================================================================================================
Name                  Type    Units        Description
===================== ======= ============ =======================================================================================================================================
TARGETID              int64                Unique DESI target ID
PETAL_LOC             int16                Petal location [0-9]
DEVICE_LOC            int32                Device location on focal plane [0-523]
LOCATION              int64                Location on the focal plane PETAL_LOC*1000 + DEVICE_LOC
FIBER                 int32                Fiber ID on the CCDs [0-4999]
FIBERSTATUS           int32                Fiber status mask. 0=good
TARGET_RA             float64 deg          Barycentric right ascension in ICRS
TARGET_DEC            float64 deg          Barycentric declination in ICRS
PMRA                  float32 mas yr^-1    proper motion in the +RA direction (already including cos(dec))
PMDEC                 float32 mas yr^-1    Proper motion in the +Dec direction
REF_EPOCH             float32 yr           Reference epoch for Gaia/Tycho astrometry. Typically 2015.5 for Gaia
LAMBDA_REF            float32 Angstrom     Requested wavelength at which targets should be centered on fibers
FA_TARGET             int64                Targeting bit internally used by fiberassign (linked with FA_TYPE)
FA_TYPE               binary               Fiberassign internal target type (science, standard, sky, safe, suppsky)
OBJTYPE               char[3]              Object type: TGT, SKY, NON, BAD
FIBERASSIGN_X         float32 mm           Fiberassign expected CS5 X location on focal plane
FIBERASSIGN_Y         float32 mm           Fiberassign expected CS5 Y location on focal plane
PRIORITY              int32                Target current priority
SUBPRIORITY           float64              Random subpriority [0-1) to break assignment ties
OBSCONDITIONS         int32                Bitmask of allowed observing conditions
RELEASE               int16                Imaging surveys release ID
BRICKNAME             char[8]              Brick name from tractor input
BRICKID               int32                Brick ID from tractor input
BRICK_OBJID           int32                Imaging Surveys OBJID on that brick
MORPHTYPE             char[4]              Imaging Surveys morphological type from Tractor
EBV                   float32 mag          Galactic extinction E(B-V) reddening from SFD98
FLUX_G                float32 nanomaggy    Flux in the Legacy Survey g-band (AB)
FLUX_R                float32 nanomaggy    Flux in the Legacy Survey r-band (AB)
FLUX_Z                float32 nanomaggy    Flux in the Legacy Survey z-band (AB)
FLUX_W1               float32 nanomaggy    WISE flux in W1 (AB)
FLUX_W2               float32 nanomaggy    WISE flux in W2 (AB)
FLUX_IVAR_G           float32 nanomaggy^-2 Inverse variance of FLUX_G (AB)
FLUX_IVAR_R           float32 nanomaggy^-2 Inverse variance of FLUX_R (AB)
FLUX_IVAR_Z           float32 nanomaggy^-2 Inverse variance of FLUX_Z (AB)
FLUX_IVAR_W1          float32 nanomaggy^-2 Inverse variance of FLUX_W1 (AB)
FLUX_IVAR_W2          float32 nanomaggy^-2 Inverse variance of FLUX_W2 (AB)
FIBERFLUX_G           float32 nanomaggy    Predicted g-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERFLUX_R           float32 nanomaggy    Predicted r-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERFLUX_Z           float32 nanomaggy    Predicted z-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERTOTFLUX_G        float32 nanomaggy    Predicted g-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
FIBERTOTFLUX_R        float32 nanomaggy    Predicted r-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
FIBERTOTFLUX_Z        float32 nanomaggy    Predicted z-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
MASKBITS              int16                Bitwise mask from the imaging indicating potential issue or blending
SERSIC                float32              Power-law index for the Sersic profile model (MORPHTYPE=&#x27;SER&#x27;)
SHAPE_R               float32 arcsec       Half-light radius of galaxy model (&gt;0)
SHAPE_E1              float32              Ellipticity component 1 of galaxy model for galaxy type MORPHTYPE
SHAPE_E2              float32              Ellipticity component 2 of galaxy model for galaxy type MORPHTYPE
REF_ID                int64                Tyc1*1,000,000+Tyc2*10+Tyc3 for Tycho-2; ``sourceid`` for Gaia DR2
REF_CAT               char[2]              Reference catalog source for star: T2 for Tycho-2, G2 for Gaia DR2, L2 for the SGA, empty otherwise
GAIA_PHOT_G_MEAN_MAG  float32 mag          Gaia G band magnitude
GAIA_PHOT_BP_MEAN_MAG float32 mag          Gaia BP band magnitude
GAIA_PHOT_RP_MEAN_MAG float32 mag          Gaia RP band magnitude
PARALLAX              float32 mas          Reference catalog parallax
PHOTSYS               char[1]              &#x27;N&#x27; for the MzLS/BASS photometric system, &#x27;S&#x27; for DECaLS
PRIORITY_INIT         int64                Target initial priority from target selection bitmasks and OBSCONDITIONS
NUMOBS_INIT           int64                Initial number of observations for target calculated across target selection bitmasks and OBSCONDITIONS
DESI_TARGET           int64                DESI (dark time program) target selection bitmask
BGS_TARGET            int64                BGS (Bright Galaxy Survey) target selection bitmask
MWS_TARGET            int64                Milky Way Survey targeting bits
SCND_TARGET           int64                Target selection bitmask for secondary programs
PLATE_RA              float64 deg          Barycentric Right Ascension in ICRS to be used by PlateMaker
PLATE_DEC             float64 deg          Barycentric Declination in ICRS to be used by PlateMaker
NUM_ITER              int64                Number of positioner iterations
FIBER_X               float64 mm           CS5 X location requested by PlateMaker
FIBER_Y               float64 mm           CS5 Y location requested by PlateMaker
DELTA_X               float64 mm           CS5 X requested minus actual position
DELTA_Y               float64 mm           CS5 Y requested minus actual position
FIBER_RA              float64 deg          RA of actual fiber position
FIBER_DEC             float64 deg          DEC of actual fiber position
EXPTIME               float64 s            Length of time shutter was open
PSF_TO_FIBER_SPECFLUX float64              fraction of light from point-like source captured by 1.5 arcsec diameter fiber given atmospheric seeing
NIGHT                 int32                Night of observation (YYYYMMDD) starting at local noon before observations start
EXPID                 int32                DESI Exposure ID number
MJD                   float64 d            Modified Julian Date when shutter was opened for this exposure
TILEID                int32                Unique DESI tile ID
===================== ======= ============ =======================================================================================================================================

HDU3
----

EXTNAME = SCORES

The table with various quality information about spectra.


Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   488              int  length of dimension 1
    NAXIS2   3572976          int  length of dimension 2
    CHECKSUM 9fTEHdQE9dQEEdQE str  HDU checksum updated 2024-12-19T17:17:33
    DATASUM  4196603941       str  data unit checksum updated 2024-12-19T17:17:33
    ======== ================ ==== ==============================================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

===================== ======= ===== ============================================================
Name                  Type    Units Description
===================== ======= ===== ============================================================
TARGETID              int64         Unique DESI target ID
SUM_RAW_COUNT_B       float64       Sum of raw counts in B camera
MEDIAN_RAW_COUNT_B    float64       Median of raw counts in B camera
MEDIAN_RAW_SNR_B      float64       Median(raw signal/noise) in B camera
SUM_FFLAT_COUNT_B     float64       Sum of fiber-flatfielded counts B camera
MEDIAN_FFLAT_COUNT_B  float64       Median of fiber-flatfielded counts in B camera
MEDIAN_FFLAT_SNR_B    float64       Median(S/N) of fiberflatfielded counts in B camera
SUM_SKYSUB_COUNT_B    float64       Sum of sky-subtracted counts in B camera
MEDIAN_SKYSUB_COUNT_B float64       Median of sky-subtracted counts in B camera
MEDIAN_SKYSUB_SNR_B   float64       Median(S/N) of sky-subtracted counts in B camera
SUM_CALIB_COUNT_B     float64       Sum of calibrated flux in B camera
MEDIAN_CALIB_COUNT_B  float64       Median of calibrated flux in B camera
MEDIAN_CALIB_SNR_B    float64       Median(S/N) of calibrated flux in B camera
TSNR2_GPBDARK_B       float64       template (S/N)^2 for dark targets in guider pass band on B
TSNR2_ELG_B           float64       ELG B template (S/N)^2
TSNR2_GPBBRIGHT_B     float64       template (S/N)^2 for bright targets in guider pass band on B
TSNR2_LYA_B           float64       LYA B template (S/N)^2
TSNR2_BGS_B           float64       BGS B template (S/N)^2
TSNR2_GPBBACKUP_B     float64       template (S/N)^2 for backup targets in guider pass band on B
TSNR2_QSO_B           float64       QSO B template (S/N)^2
TSNR2_LRG_B           float64       LRG B template (S/N)^2
SUM_RAW_COUNT_R       float64       Sum of raw counts in R camera
MEDIAN_RAW_COUNT_R    float64       Median of raw counts in R camera
MEDIAN_RAW_SNR_R      float64       Median(raw signal/noise) in R camera
SUM_FFLAT_COUNT_R     float64       Sum of fiber-flatfielded counts R camera
MEDIAN_FFLAT_COUNT_R  float64       Median of fiber-flatfielded counts in R camera
MEDIAN_FFLAT_SNR_R    float64       Median(S/N) of fiberflatfielded counts in R camera
SUM_SKYSUB_COUNT_R    float64       Sum of sky-subtracted counts in R camera
MEDIAN_SKYSUB_COUNT_R float64       Median of sky-subtracted counts in R camera
MEDIAN_SKYSUB_SNR_R   float64       Median(S/N) of sky-subtracted counts in R camera
SUM_CALIB_COUNT_R     float64       Sum of calibrated flux in R camera
MEDIAN_CALIB_COUNT_R  float64       Median of calibrated flux in R camera
MEDIAN_CALIB_SNR_R    float64       Median(S/N) of calibrated flux in R camera
TSNR2_GPBDARK_R       float64       template (S/N)^2 for dark targets in guider pass band on R
TSNR2_ELG_R           float64       ELG R template (S/N)^2
TSNR2_GPBBRIGHT_R     float64       template (S/N)^2 for bright targets in guider pass band on R
TSNR2_LYA_R           float64       LYA R template (S/N)^2
TSNR2_BGS_R           float64       BGS R template (S/N)^2
TSNR2_GPBBACKUP_R     float64       template (S/N)^2 for backup targets in guider pass band on R
TSNR2_QSO_R           float64       QSO R template (S/N)^2
TSNR2_LRG_R           float64       LRG R template (S/N)^2
SUM_RAW_COUNT_Z       float64       Sum of raw counts in Z camera
MEDIAN_RAW_COUNT_Z    float64       Median of raw counts in Z camera
MEDIAN_RAW_SNR_Z      float64       Median(raw signal/noise) in Z camera
SUM_FFLAT_COUNT_Z     float64       Sum of fiber-flatfielded counts Z camera
MEDIAN_FFLAT_COUNT_Z  float64       Median of fiber-flatfielded counts in Z camera
MEDIAN_FFLAT_SNR_Z    float64       Median(S/N) of fiberflatfielded counts in Z camera
SUM_SKYSUB_COUNT_Z    float64       Sum of sky-subtracted counts in Z camera
MEDIAN_SKYSUB_COUNT_Z float64       Median of sky-subtracted counts in Z camera
MEDIAN_SKYSUB_SNR_Z   float64       Median(S/N) of sky-subtracted counts in Z camera
SUM_CALIB_COUNT_Z     float64       Sum of calibrated flux in Z camera
MEDIAN_CALIB_COUNT_Z  float64       Median of calibrated flux in Z camera
MEDIAN_CALIB_SNR_Z    float64       Median(S/N) of calibrated flux in Z camera
TSNR2_GPBDARK_Z       float64       template (S/N)^2 for dark targets in guider pass band on Z
TSNR2_ELG_Z           float64       ELG Z template (S/N)^2
TSNR2_GPBBRIGHT_Z     float64       template (S/N)^2 for bright targets in guider pass band on Z
TSNR2_LYA_Z           float64       LYA Z template (S/N)^2
TSNR2_BGS_Z           float64       BGS Z template (S/N)^2
TSNR2_GPBBACKUP_Z     float64       template (S/N)^2 for backup targets in guider pass band on Z
TSNR2_QSO_Z           float64       QSO Z template (S/N)^2
TSNR2_LRG_Z           float64       LRG Z template (S/N)^2
===================== ======= ===== ============================================================

HDU4
----

EXTNAME = GAIA

The Gaia DR3 measurements for each object in the catalog.                              

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   438              int  length of dimension 1
    NAXIS2   3572976          int  length of dimension 2
    CHECKSUM EB5AH929EA2AE927 str  HDU checksum updated 2024-12-19T17:18:07
    DATASUM  3494719464       str  data unit checksum updated 2024-12-19T17:18:07
    ======== ================ ==== ==============================================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

=============================== ======= ========= ====================================================================
Name                            Type    Units     Description
=============================== ======= ========= ====================================================================
SOURCE_ID                       int64
RANDOM_INDEX                    int64
REF_EPOCH                       float64 yr        Reference epoch for Gaia/Tycho astrometry. Typically 2015.5 for Gaia
RA                              float64 deg       Barycentric Right Ascension in ICRS
RA_ERROR                        float32
DEC                             float64 deg       Barycentric declination in ICRS
DEC_ERROR                       float32
PARALLAX                        float64 mas       Reference catalog parallax
PARALLAX_ERROR                  float32
PARALLAX_OVER_ERROR             float32
PMRA                            float64 mas yr^-1 proper motion in the +RA direction (already including cos(dec))
PMRA_ERROR                      float32
PMDEC                           float64 mas yr^-1 Proper motion in the +Dec direction
PMDEC_ERROR                     float32
RA_DEC_CORR                     float32
RA_PARALLAX_CORR                float32
RA_PMRA_CORR                    float32
RA_PMDEC_CORR                   float32
DEC_PARALLAX_CORR               float32
DEC_PMRA_CORR                   float32
DEC_PMDEC_CORR                  float32
PARALLAX_PMRA_CORR              float32
PARALLAX_PMDEC_CORR             float32
PMRA_PMDEC_CORR                 float32
ASTROMETRIC_N_OBS_AL            int16
ASTROMETRIC_N_OBS_AC            int16
ASTROMETRIC_N_GOOD_OBS_AL       int16
ASTROMETRIC_N_BAD_OBS_AL        int16
ASTROMETRIC_GOF_AL              float32
ASTROMETRIC_CHI2_AL             float32
ASTROMETRIC_EXCESS_NOISE        float32
ASTROMETRIC_EXCESS_NOISE_SIG    float32
ASTROMETRIC_PARAMS_SOLVED       int16
ASTROMETRIC_PRIMARY_FLAG        logical
NU_EFF_USED_IN_ASTROMETRY       float32
PSEUDOCOLOUR                    float32
PSEUDOCOLOUR_ERROR              float32
RA_PSEUDOCOLOUR_CORR            float32
DEC_PSEUDOCOLOUR_CORR           float32
PARALLAX_PSEUDOCOLOUR_CORR      float32
PMRA_PSEUDOCOLOUR_CORR          float32
PMDEC_PSEUDOCOLOUR_CORR         float32
ASTROMETRIC_MATCHED_TRANSITS    int16
VISIBILITY_PERIODS_USED         int16
ASTROMETRIC_SIGMA5D_MAX         float32
MATCHED_TRANSITS                int16
NEW_MATCHED_TRANSITS            int16
MATCHED_TRANSITS_REMOVED        int16
IPD_GOF_HARMONIC_AMPLITUDE      float32
IPD_GOF_HARMONIC_PHASE          float32
IPD_FRAC_MULTI_PEAK             int16
IPD_FRAC_ODD_WIN                int16
RUWE                            float32
DUPLICATED_SOURCE               logical
PHOT_G_N_OBS                    int16
PHOT_G_MEAN_FLUX                float64
PHOT_G_MEAN_FLUX_ERROR          float32
PHOT_G_MEAN_FLUX_OVER_ERROR     float32
PHOT_G_MEAN_MAG                 float32
PHOT_BP_N_OBS                   int16
PHOT_BP_MEAN_FLUX               float64
PHOT_BP_MEAN_FLUX_ERROR         float32
PHOT_BP_MEAN_FLUX_OVER_ERROR    float32
PHOT_BP_MEAN_MAG                float32
PHOT_RP_N_OBS                   int16
PHOT_RP_MEAN_FLUX               float64
PHOT_RP_MEAN_FLUX_ERROR         float32
PHOT_RP_MEAN_FLUX_OVER_ERROR    float32
PHOT_RP_MEAN_MAG                float32
PHOT_BP_RP_EXCESS_FACTOR        float32
PHOT_BP_N_CONTAMINATED_TRANSITS int16
PHOT_BP_N_BLENDED_TRANSITS      int16
PHOT_RP_N_CONTAMINATED_TRANSITS int16
PHOT_RP_N_BLENDED_TRANSITS      int16
PHOT_PROC_MODE                  int16
BP_RP                           float32
BP_G                            float32
G_RP                            float32
RADIAL_VELOCITY                 float32
RADIAL_VELOCITY_ERROR           float32
RV_METHOD_USED                  int16
RV_NB_TRANSITS                  int16
RV_NB_DEBLENDED_TRANSITS        int16
RV_VISIBILITY_PERIODS_USED      int16
RV_EXPECTED_SIG_TO_NOISE        float32
RV_RENORMALISED_GOF             float32
RV_CHISQ_PVALUE                 float32
RV_TIME_DURATION                float32
RV_AMPLITUDE_ROBUST             float32
RV_TEMPLATE_TEFF                float32
RV_TEMPLATE_LOGG                float32
RV_TEMPLATE_FE_H                float32
RV_ATM_PARAM_ORIGIN             int16
VBROAD                          float32
VBROAD_ERROR                    float32
VBROAD_NB_TRANSITS              int16
GRVS_MAG                        float32
GRVS_MAG_ERROR                  float32
GRVS_MAG_NB_TRANSITS            int16
RVS_SPEC_SIG_TO_NOISE           float32
ECL_LON                         float64
ECL_LAT                         float64
IN_QSO_CANDIDATES               logical
IN_GALAXY_CANDIDATES            logical
NON_SINGLE_STAR                 int16
HAS_XP_CONTINUOUS               logical
HAS_XP_SAMPLED                  logical
HAS_RVS                         logical
HAS_EPOCH_PHOTOMETRY            logical
HAS_EPOCH_RV                    logical
IN_ANDROMEDA_SURVEY             logical
CLASSPROB_DSC_COMBMOD_QUASAR    float32
CLASSPROB_DSC_COMBMOD_GALAXY    float32
CLASSPROB_DSC_COMBMOD_STAR      float32
TEFF_GSPPHOT                    float32
LOGG_GSPPHOT                    float32
MH_GSPPHOT                      float32
EBV                             float32 mag       Galactic extinction E(B-V) reddening from SFD98
=============================== ======= ========= ====================================================================


Notes and Examples
==================

*Add notes and examples here.  You can also create links to example files.*
