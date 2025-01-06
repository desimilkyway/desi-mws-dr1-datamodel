===========
spmod_coadd
===========

:Summary: This is the file containing the best-fit models to spectra from FERRE for a given healpix.
:Naming Convention: ``spmod_coadd-{SURVEY}-{PROGRAM}-{HEALPIX}.fits``, where
    SURVEY is main, special, sv1, sv2, sv3, and PROGRAM is dark, bright, 
    backup, other.
:Regex: ``spmod_coadd-.*-.*-.*.fits`` 
:File Type: FITS, 50 MB  

Contents
========

====== ============ ======== ===================
Number EXTNAME      Type     Contents
====== ============ ======== ===================
HDU00_              IMAGE    Empty HDU
HDU01_ B_WAVELENGTH IMAGE    Wavelength array of b-channel spectra
HDU02_ B_MODEL      BINTABLE Flux array of best-fit model b-channel spectra and auxiliary quantities 
HDU03_ R_WAVELENGTH IMAGE    Wavelength array of r-channel spectra
HDU04_ R_MODEL      BINTABLE Flux array of best-fit model r-channel spectra and auxiliary quantities                                                        
HDU05_ Z_WAVELENGTH IMAGE    Wavelength array of z-channel spectra
HDU06_ Z_MODEL      BINTABLE Flux array of best-fit model z-channel spectra and auxiliary quantities                                                        
HDU07_ FIBERMAP     BINTABLE Information about objects inherited from targeting
HDU08_ SCORES       BINTABLE Information about spectra quality
HDU09_ FILTER       BINTABLE Spectral filters used for the determination of chemical abundances
====== ============ ======== ===================


FITS Header Units
=================

HDU00
-----

Empty HDU.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ========================== ===== =================================
    KEY      Example Value              Type  Comment
    ======== ========================== ===== =================================
    DATE     2022-04-03T16:48:32        str   Date of processing
    FCONFIG  desi-ms.yaml               str   FERRE config information
    HOST     login1                     str   machine used
    OS       posix                      str   Operative system
    PLATFORM Linux 4.4.90-92.45-default str   OS details
    NSPEC    7                          int   Number of spectra included
    FTIME    234.041                    float Compute time used by FERRE
    STIME    900.0                      float Compute time estimated for Slurm
    NCORES   16                         int   Number of cores in node
    NTHREADS 12                         int   Maximum number of cores for FERRE 
    NUMPY    1.17.2                     str   NumPy version
    ASTROPY  3.2.2                      str   AstroPy version
    MATPLOTL 3.1.1                      str   Matplotlib version
    SCIPY    1.3.1                      str   SciPy version
    YAML     5.1.2                      str   Yaml version
    PYTHON   3.7.4                      str   Python version
    PIFERRE  0.4                        str   Piferre version
    FERRE    5.0.0                      str   FERRE version
    ======== ========================== ===== =================================


HDU01
-----

EXTNAME = B_WAVELENGTH

Wavelength array for the b-channel spectra. 

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =======
    KEY    Example Value Type Comment
    ====== ============= ==== =======
    NAXIS1 4759          int
    ====== ============= ==== =======

Data: FITS image [float64, 4759]

HDU02
-----

EXTNAME = B_MODEL

Best-fit b-channel model fluxes and associated quantities.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 190360        int  length of dimension 1
    NAXIS2 7             int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

==== ============= ===== ===========
Name Type          Units Description
==== ============= ===== ===========
obs  float64[4759] cgs   Normalized b-channel observed flux as fit by FERRE 
err  float64[4759] cgs   Normalized b-channel observed flux uncertainties
flx  float64[4759] cgs   Best-fit b-channel model flux in absolute units (f_lambda in cgs units)
fit  float64[4759] cgs   Best-fit b-channel normalized model flux 
abu  float64[4759] cgs   Best-fit b-channel normalized model flux from the chemical abundance determinations
==== ============= ===== ===========

HDU03
-----

EXTNAME = R_WAVELENGTH

Wavelength array for the r-channel spectra.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =======
    KEY    Example Value Type Comment
    ====== ============= ==== =======
    NAXIS1 4231          int
    ====== ============= ==== =======

Data: FITS image [float64, 4231]

HDU04
-----

EXTNAME = R_MODEL

Best-fit r-channel model fluxes and associated quantities.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 169240        int  length of dimension 1
    NAXIS2 7             int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

==== ============= ===== ===========
Name Type          Units Description
==== ============= ===== ===========
obs  float64[4231] cgs   Normalized r-channel observed flux as fit by FERRE
err  float64[4231] cgs   Normalized r-channel observed flux uncertainties
flx  float64[4231] cgs   Best-fit r-channel model flux in absolute units (f_lambda in cgs units)
fit  float64[4231] cgs   Best-fit r-channel normalized model flux
abu  float64[4231] cgs   Best-fit r-channel normalized model flux from the chemical abundance determinations
==== ============= ===== ===========

HDU05
-----

EXTNAME = Z_WAVELENGTH

Wavelength array for the z-channel spectra.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =======
    KEY    Example Value Type Comment
    ====== ============= ==== =======
    NAXIS1 4797          int
    ====== ============= ==== =======

Data: FITS image [float64, 4797]

HDU06
-----

EXTNAME = Z_MODEL

Best-fit z-channel model fluxes and associated quantities.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 191880        int  length of dimension 1
    NAXIS2 7             int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

==== ============= ===== ===========
Name Type          Units Description
==== ============= ===== ===========
obs  float64[4797] cgs   Normalized z-channel observed flux as fit by FERRE
err  float64[4797] cgs   Normalized z-channel observed flux uncertainties
flx  float64[4797] cgs   Best-fit z-channel model flux in absolute units (f_lambda in cgs units)
fit  float64[4797] cgs   Best-fit z-channel normalized model flux
abu  float64[4797] cgs   Best-fit z-channel normalized model flux from the chemical abundance determinations
==== ============= ===== ===========

HDU07
-----

EXTNAME = FIBERMAP

The FIBERMAP targeting table for the objects. The same and in the same order 
  as in SPTAB.

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

HDU08
-----

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

HDU09
-----

EXTNAME = FILTER

*Summarize the contents of this HDU.*

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ====== ============= ==== =====================
    KEY    Example Value Type Comment
    ====== ============= ==== =====================
    NAXIS1 32            int  length of dimension 1
    NAXIS2 13787         int  length of dimension 2
    ====== ============= ==== =====================

Required Data Table Columns
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. rst-class:: columns

==== ======= ===== ===========
Name Type    Units Description
==== ======= ===== ===========
Fe   float64       FERRE array of weights used to derive the iron abundance  
Ca   float64       FERRE array of weights used to derive the calcium abundance
C    float64       FERRE array of weights used to derive the carbon abundance
Mg   float64       FERRE array of weights used to derive the magnesium abundance
==== ======= ===== ===========


Notes and Examples
==================
 
https://data.desi.lbl.gov/desi/science/mws/redux/edr/v1/sp_output/220309/healpix/sv3/dark/105/10517/spmod_coadd-sv3-dark-10517.fits
