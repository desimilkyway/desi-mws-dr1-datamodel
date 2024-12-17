===========
sptab_coadd
===========

:Summary: FERRE results from coadded spectra for a given HEALPIX.
:Naming Convention: ``sptab_coadd-{SURVEY}-{PROGRAM}-{HEALPIX}.fits``, where 
    SURVEY is main, special, sv1, sv2, sv3, and PROGRAM is dark, bright, 
    backup, other.
:Regex: ``sptab_coadd-.*-.*-.*.fits`` 
:File Type: FITS, 100 KB  

Contents
========

====== ======== ======== ===================
Number EXTNAME  Type     Contents
====== ======== ======== ===================
HDU0_           IMAGE    Empty HDU
HDU1_  SPTAB    BINTABLE FERRE results
HDU2_  FIBERMAP BINTABLE Information about objects inherited from targeting
HDU3_  SCORES   BINTABLE Information about spectra quality
HDU4_  AUX      BINTABLE Auxiliary information: names of the parameters and chemical elements in the order used in building the PARAM and ELEM arrays in SPTAB
====== ======== ======== ===================


FITS Header Units
=================

HDU0
----

Empty HDU.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ========================== ===== =======
    KEY      Example Value              Type  Comment
    ======== ========================== ===== =======
    DATE     2022-04-03T16:48:32        str   Date of processing
    FCONFIG  desi-ms.yaml               str   FERRE config information
    HOST     login1                     str   machine used
    OS       posix                      str   Operative system
    PLATFORM Linux 4.4.90-92.45-default str   OS details
    NSPEC    7                          int   Number of spectra included
    FTIME    234.041                    float Compute time used by FERRE
    STIME    900.0                      float Compute time estimated for Slurm
    NCORES   16                         int   Number of cores in node
    NTHREADS 12                         int   Number of cores used by large FERRE instances
    NUMPY    1.17.2                     str   NumPy version
    ASTROPY  3.2.2                      str   AstroPy version
    MATPLOTL 3.1.1                      str   Matplotlib version
    SCIPY    1.3.1                      str   SciPy version
    YAML     5.1.2                      str   Yaml version
    PYTHON   3.7.4                      str   Python version
    PIFERRE  0.4                        str   Piferre version
    FERRE    5.0.0                      str   FERRE version
    ======== ========================== ===== =======


HDU1
----

EXTNAME = SPTAB

This is the table of measurements by FERRE of coadded DESI spectra for a given HEALPIX.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 448           int  length of dimension 1
    NAXIS2 7             int  length of dimension 2
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
    NAXIS1 341           int  length of dimension 1
    NAXIS2 7             int  length of dimension 2
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
SV3_DESI_TARGET            int64                DESI (dark time program) target selection bitmask for SV3
SV3_BGS_TARGET             int64                BGS (bright time program) target selection bitmask for SV3
SV3_MWS_TARGET             int64                MWS (bright time program) target selection bitmask for SV3
SV3_SCND_TARGET            int64                Secondary target selection bitmask for SV3
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
    NAXIS2 7             int  length of dimension 2
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

EXTNAME = AUX

Additional information on the order of the parameters and elements in the arrays PARAM and ELEM, respectively.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 232           int  length of dimension 1
    NAXIS2 1             int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

==== ========= ===== ===========
Name Type      Units Description
==== ========= ===== ===========
p    char[200]
e    char[32]
==== ========= ===== ===========


Notes and Examples
==================

Example:
https://data.desi.lbl.gov/desi/science/mws/redux/edr/v1/sp_output/220309/healpix/sv3/dark/105/10517/sptab_coadd-sv3-dark-10517.fits 
