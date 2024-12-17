=====
sppix
=====

:Summary: FERRE results from coadded spectra for different surveys, programs.
:Naming Convention: ``sppix-{SURVEY}-{PROGRAM}.fits``, where SURVEY is main, 
   special, sv1, sv2, sv3, and PROGRAM is dark, bright, backup, other.
:Regex: ``sppix-.*-.*fits``
:File Type: FITS, 100 MB  

Contents
========

====== ======== ======== ===================
Number EXTNAME  Type     Contents
====== ======== ======== ===================
HDU0_           IMAGE    Empty HDU
HDU1_  SPTAB    BINTABLE FERRE results
HDU2_  FIBERMAP BINTABLE Information about objects inherited from targeting
HDU3_  SCORES   BINTABLE Information about spectra quality
HDU4_  GAIA     BINTABLE Gaia crossmatch
====== ======== ======== ===================


FITS Header Units
=================

HDU0
----

Empty HDU.

HDU1
----

EXTNAME = SPTAB

This is the table of measurements by FERRE of coadded DESI spectra for given survey/program.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 454           int  length of dimension 1
    NAXIS2 728           int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

========== =========== ====== ===================================================================================================
Name       Type        Units  Description
========== =========== ====== ===================================================================================================
SUCCESS    int64              Bit indicating whether the code has likely produced useful results
TARGETID   int64              Unique DESI target ID
TARGET_RA  float64     deg    Target right ascension
TARGET_DEC float64     deg    Target declination
REF_ID     int64              Tyc1*1,000,000+Tyc2*10+Tyc3 for Tycho-2; sourceid for Gaia DR2
REF_CAT    char[2]            Reference catalog source for star: T2 for Tycho-2, G2 for Gaia DR2, L2 for the SGA, empty otherwise
SRCFILE    char[20]           DESI data file
BESTGRID   char[8]            Model grid that produced the best fit
TEFF       float64     K      Effective temperature (K)
LOGG       float64            Surface gravity (g in cm/s**2)
FEH        float64            Metallicity [Fe/H] = log10(N(Fe)/N(H)) - log10(N(Fe)/N(H))sun
ALPHAFE    float64            Alpha-to-iron ratio [alpha/Fe]
LOG10MICRO float64            Log10 of Microturbulence (km/s)
PARAM      float64[5]         Array of atmospheric parameters ([Fe/H], [a/Fe], log10micro, Teff,logg)
COVAR      float64[25]        Covariance matrix for ([Fe/H], [a/Fe], log10micro, Teff,logg)
ELEM       float64[4]         Elemental abundance ratios to hydrogen [elem/H]
ELEM_ERR   float64[4]         Uncertainties in the elemental abundance ratios
CHISQ_TOT  float64            Total chi**2
SNR_MED    float64            Median signal-to-ratio
RV_ADOP    float64     km s-1 Adopted Radial Velocity (km/s)
RV_ERR     float64     km s-1 Uncertainty in the adopted Radial Velocity (km/s)
HEALPIX    int64              HEALPixel containing this location at NSIDE=64 in the NESTED scheme
========== =========== ====== ===================================================================================================

HDU2
----

EXTNAME = FIBERMAP

FIBERMAP table with information on individual targets copied from original coadd file.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 317           int  length of dimension 1
    NAXIS2 728           int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

========================== ======= ============ ===============================================================================================================================
Name                       Type    Units        Description
========================== ======= ============ ===============================================================================================================================
TARGETID                   int64                Unique DESI target ID
COADD_FIBERSTATUS          int32                bitwise-AND of input FIBERSTATUS
TARGET_RA                  float64 deg          Target right ascension
TARGET_DEC                 float64 deg          Target declination
PMRA                       float32 mas yr^-1    proper motion in the +RA direction (already including cos(dec))
PMDEC                      float32 mas yr^-1    Proper motion in the +Dec direction
REF_EPOCH                  float32 yr           Reference epoch for Gaia/Tycho astrometry. Typically 2015.5 for Gaia
FA_TARGET                  int64                Targeting bit internally used by fiberassign (linked with FA_TYPE)
FA_TYPE                    binary               Fiberassign internal target type (science, standard, sky, safe, suppsky)
OBJTYPE                    char[3]              Object type: TGT, SKY, NON, BAD
SUBPRIORITY                float64              Random subpriority [0-1) to break assignment ties
OBSCONDITIONS              int32                Bitmask of allowed observing conditions
RELEASE                    int16                Imaging surveys release ID
BRICKNAME                  char[8]              Brick name from tractor input
BRICKID                    int32                Brick ID from tractor input
BRICK_OBJID                int32                Imaging Surveys OBJID on that brick
MORPHTYPE                  char[4]              Imaging Surveys morphological type from Tractor
EBV                        float32 mag          Galactic extinction E(B-V) reddening from SFD98
FLUX_G                     float32 nanomaggy    Flux in the Legacy Survey g-band (AB)
FLUX_R                     float32 nanomaggy    Flux in the Legacy Survey r-band (AB)
FLUX_Z                     float32 nanomaggy    Flux in the Legacy Survey z-band (AB)
FLUX_W1                    float32 nanomaggy    WISE flux in W1 (AB)
FLUX_W2                    float32 nanomaggy    WISE flux in W2 (AB)
FLUX_IVAR_G                float32 nanomaggy^-2 Inverse variance of FLUX_G (AB)
FLUX_IVAR_R                float32 nanomaggy^-2 Inverse variance of FLUX_R (AB)
FLUX_IVAR_Z                float32 nanomaggy^-2 Inverse variance of FLUX_Z (AB)
FLUX_IVAR_W1               float32 nanomaggy^-2 Inverse variance of FLUX_W1 (AB)
FLUX_IVAR_W2               float32 nanomaggy^-2 Inverse variance of FLUX_W2 (AB)
FIBERFLUX_G                float32 nanomaggy    Predicted g-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERFLUX_R                float32 nanomaggy    Predicted r-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERFLUX_Z                float32 nanomaggy    Predicted z-band flux within a fiber of diameter 1.5 arcsec from this object in 1 arcsec Gaussian seeing
FIBERTOTFLUX_G             float32 nanomaggy    Predicted g-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
FIBERTOTFLUX_R             float32 nanomaggy    Predicted r-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
FIBERTOTFLUX_Z             float32 nanomaggy    Predicted z-band flux within a fiber of diameter 1.5 arcsec from all sources at this location in 1 arcsec Gaussian seeing
MASKBITS                   int16                Bitwise mask from the imaging indicating potential issue or blending
SERSIC                     float32              Power-law index for the Sersic profile model (MORPHTYPE=SER)
SHAPE_R                    float32 arcsec       Half-light radius of galaxy model (&gt;0)
SHAPE_E1                   float32              Ellipticity component 1 of galaxy model for galaxy type MORPHTYPE
SHAPE_E2                   float32              Ellipticity component 2 of galaxy model for galaxy type MORPHTYPE
REF_ID                     int64                Tyc1*1,000,000+Tyc2*10+Tyc3 for Tycho-2; sourceid for Gaia DR2
REF_CAT                    char[2]              Reference catalog source for star: T2 for Tycho-2, G2 for Gaia DR2, L2 for the SGA, empty otherwise
GAIA_PHOT_G_MEAN_MAG       float32 mag          Gaia G band magnitude
GAIA_PHOT_BP_MEAN_MAG      float32 mag          Gaia BP band magnitude
GAIA_PHOT_RP_MEAN_MAG      float32 mag          Gaia RP band magnitude
PARALLAX                   float32 mas          Reference catalog parallax
PHOTSYS                    char[1]              N for the MzLS/BASS photometric system, S for DECaLS
PRIORITY_INIT              int64                Target initial priority from target selection bitmasks and OBSCONDITIONS
NUMOBS_INIT                int64                Initial number of observations for target calculated across target selection bitmasks and OBSCONDITIONS
CMX_TARGET                 int64                Target selection bitmask for commissioning
DESI_TARGET                int64                DESI (dark time program) target selection bitmask
BGS_TARGET                 int64                BGS (Bright Galaxy Survey) target selection bitmask
MWS_TARGET                 int64                Milky Way Survey targeting bits
PLATE_RA                   float64 deg          Right Ascension to be used by PlateMaker
PLATE_DEC                  float64 deg          Declination to be used by PlateMaker
COADD_NUMEXP               int16                Number of exposures in coadd
COADD_EXPTIME              float32 s            Summed exposure time for coadd
COADD_NUMNIGHT             int16                Number of nights in coadd
COADD_NUMTILE              int16                Number of tiles in coadd
MEAN_DELTA_X               float32 mm           Mean (over exposures) fiber difference requested - actual CS5 X location on focal plane
RMS_DELTA_X                float32 mm           RMS (over exposures) of the fiber difference between measured and requested CS5 X location on focal plane
MEAN_DELTA_Y               float32 mm           Mean (over exposures) fiber difference requested - actual CS5 Y location on focal plane
RMS_DELTA_Y                float32 mm           RMS (over exposures) of the fiber difference between measured and requested CS5 Y location on focal plane
MEAN_FIBER_RA              float64 deg          Mean (over exposures) RA of actual fiber position
STD_FIBER_RA               float32 arcsec       Standard deviation (over exposures) of RA of actual fiber position
MEAN_FIBER_DEC             float64 deg          Mean (over exposures) DEC of actual fiber position
STD_FIBER_DEC              float32 arcsec       Standard deviation (over exposures) of DEC of actual fiber position
MEAN_PSF_TO_FIBER_SPECFLUX float32              Mean of input exposures fraction of light from point-like source captured by 1.5 arcsec diameter fiber given atmospheric seeing
========================== ======= ============ ===============================================================================================================================

HDU3
----

EXTNAME = SCORES

The table with various quality information about spectra.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 172           int  length of dimension 1
    NAXIS2 728           int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

=================== ======= ===== ======================================
Name                Type    Units Description
=================== ======= ===== ======================================
TARGETID            int64         Unique DESI target ID
INTEG_COADD_FLUX_B  float32
MEDIAN_COADD_FLUX_B float32
MEDIAN_COADD_SNR_B  float32
INTEG_COADD_FLUX_R  float32
MEDIAN_COADD_FLUX_R float32
MEDIAN_COADD_SNR_R  float32
INTEG_COADD_FLUX_Z  float32
MEDIAN_COADD_FLUX_Z float32
MEDIAN_COADD_SNR_Z  float32
TSNR2_GPBDARK_B     float32
TSNR2_ELG_B         float32       ELG B template (S/N)^2
TSNR2_GPBBRIGHT_B   float32
TSNR2_LYA_B         float32       LYA B template (S/N)^2
TSNR2_BGS_B         float32       BGS B template (S/N)^2
TSNR2_GPBBACKUP_B   float32
TSNR2_QSO_B         float32       QSO B template (S/N)^2
TSNR2_LRG_B         float32       LRG B template (S/N)^2
TSNR2_GPBDARK_R     float32
TSNR2_ELG_R         float32       ELG R template (S/N)^2
TSNR2_GPBBRIGHT_R   float32
TSNR2_LYA_R         float32       LYA R template (S/N)^2
TSNR2_BGS_R         float32       BGS R template (S/N)^2
TSNR2_GPBBACKUP_R   float32
TSNR2_QSO_R         float32       QSO R template (S/N)^2
TSNR2_LRG_R         float32       LRG R template (S/N)^2
TSNR2_GPBDARK_Z     float32
TSNR2_ELG_Z         float32       ELG Z template (S/N)^2
TSNR2_GPBBRIGHT_Z   float32
TSNR2_LYA_Z         float32       LYA Z template (S/N)^2
TSNR2_BGS_Z         float32       BGS Z template (S/N)^2
TSNR2_GPBBACKUP_Z   float32
TSNR2_QSO_Z         float32       QSO Z template (S/N)^2
TSNR2_LRG_Z         float32       LRG Z template (S/N)^2
TSNR2_GPBDARK       float32
TSNR2_ELG           float32       ELG template (S/N)^2 summed over B,R,Z
TSNR2_GPBBRIGHT     float32
TSNR2_LYA           float32       LYA template (S/N)^2 summed over B,R,Z
TSNR2_BGS           float32       BGS template (S/N)^2 summed over B,R,Z
TSNR2_GPBBACKUP     float32
TSNR2_QSO           float32       QSO template (S/N)^2 summed over B,R,Z
TSNR2_LRG           float32       LRG template (S/N)^2 summed over B,R,Z
=================== ======= ===== ======================================

HDU4
----

EXTNAME = GAIA

The Gaia DR3 measurements for each object in the catalog.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 632           int  length of dimension 1
    NAXIS2 728           int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

=============================== ======== ========= ====================================================================
Name                            Type     Units     Description
=============================== ======== ========= ====================================================================
SOLUTION_ID                     int64
DESIGNATION                     char[20]
SOURCE_ID                       int64
RANDOM_INDEX                    int64
REF_EPOCH                       float64  yr        Reference epoch for Gaia/Tycho astrometry. Typically 2015.5 for Gaia
RA                              float64  deg       Target Right Ascension
RA_ERROR                        float32
DEC                             float64  deg       Target declination
DEC_ERROR                       float32
PARALLAX                        float64  mas       Reference catalog parallax
PARALLAX_ERROR                  float32
PARALLAX_OVER_ERROR             float32
PM                              float32
PMRA                            float64  mas yr^-1 proper motion in the +RA direction (already including cos(dec))
PMRA_ERROR                      float32
PMDEC                           float64  mas yr^-1 Proper motion in the +Dec direction
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
SCAN_DIRECTION_STRENGTH_K1      float32
SCAN_DIRECTION_STRENGTH_K2      float32
SCAN_DIRECTION_STRENGTH_K3      float32
SCAN_DIRECTION_STRENGTH_K4      float32
SCAN_DIRECTION_MEAN_K1          float32
SCAN_DIRECTION_MEAN_K2          float32
SCAN_DIRECTION_MEAN_K3          float32
SCAN_DIRECTION_MEAN_K4          float32
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
PHOT_VARIABLE_FLAG              char[20]
L                               float64
B                               float64
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
HAS_MCMC_GSPPHOT                logical
HAS_MCMC_MSC                    logical
IN_ANDROMEDA_SURVEY             logical
CLASSPROB_DSC_COMBMOD_QUASAR    float32
CLASSPROB_DSC_COMBMOD_GALAXY    float32
CLASSPROB_DSC_COMBMOD_STAR      float32
TEFF_GSPPHOT                    float32
TEFF_GSPPHOT_LOWER              float32
TEFF_GSPPHOT_UPPER              float32
LOGG_GSPPHOT                    float32
LOGG_GSPPHOT_LOWER              float32
LOGG_GSPPHOT_UPPER              float32
MH_GSPPHOT                      float32
MH_GSPPHOT_LOWER                float32
MH_GSPPHOT_UPPER                float32
DISTANCE_GSPPHOT                float32
DISTANCE_GSPPHOT_LOWER          float32
DISTANCE_GSPPHOT_UPPER          float32
AZERO_GSPPHOT                   float32
AZERO_GSPPHOT_LOWER             float32
AZERO_GSPPHOT_UPPER             float32
AG_GSPPHOT                      float32
AG_GSPPHOT_LOWER                float32
AG_GSPPHOT_UPPER                float32
EBPMINRP_GSPPHOT                float32
EBPMINRP_GSPPHOT_LOWER          float32
EBPMINRP_GSPPHOT_UPPER          float32
LIBNAME_GSPPHOT                 char[20]
EBV                             float32  mag       Galactic extinction E(B-V) reddening from SFD98
=============================== ======== ========= ====================================================================


Notes and Examples
==================

Example
https://data.desi.lbl.gov/desi/science/mws/redux/edr/v1/sp_output/sppix-sv3-bright.fits 
