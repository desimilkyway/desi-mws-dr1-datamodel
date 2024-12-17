===========
rvmod_coadd
===========

:Summary: This is the file containing the best fit models to spectra from rvspecfit
:Naming Convention: ``rvmod_coadd-sv3-bright-10016.fits`` for a sv3 survey, bright
		    program and healpixel 10016
:File Type: FITS, 551 KB  *This section gives the type of the file
    and its approximate size.*

Contents
========

====== ============ ======== ===================
Number EXTNAME      Type     Contents
====== ============ ======== ===================
HDU0_               IMAGE    Empty HDU
HDU1_  B_WAVELENGTH IMAGE    Wavelength array of b-channel spectra
HDU2_  B_MODEL      IMAGE    Flux array of best-fit model b-channel spectra 
HDU3_  R_WAVELENGTH IMAGE    Wavelength array of r-channel spectra
HDU4_  R_MODEL      IMAGE    Flux array of best-fit model r-channel spectra
HDU5_  Z_WAVELENGTH IMAGE    Wavelength array of z-channel spectra
HDU6_  Z_MODEL      IMAGE    Flux array of best-fit model z-channel spectra
HDU7_  FIBERMAP     BINTABLE Information about objects inherited from targeting
====== ============ ======== ===================


FITS Header Units
=================

HDU0
----

Empty

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ===================================================================== ==== ==============================================
    KEY      Example Value                                                         Type Comment
    ======== ===================================================================== ==== ==============================================
    TMPLCON0 desi_b                                                                str  Spec arm config name
    TMPLREV0 v211202                                                               str  Spec template revision
    TMPLSVR0 0.1.0.210117+devfee7ee                                                str  Spec template soft version
    TMPLCON1 desi_r                                                                str  Spec arm config name
    TMPLREV1 v211202                                                               str  Spec template revision
    TMPLSVR1 0.1.0.210117+devfee7ee                                                str  Spec template soft version
    TMPLCON2 desi_z                                                                str  Spec arm config name
    TMPLREV2 v211202                                                               str  Spec template revision
    TMPLSVR2 0.1.0.210117+devfee7ee                                                str  Spec template soft version
    RVS_CONF /global/cfs/cdirs/desi/science/mws/scripts/configs/config_211202.yaml str
    SPGRP    healpix                                                               str
    SPGRPVAL 10016                                                                 int
    HPXPIXEL 10016                                                                 int
    HPXNSIDE 64                                                                    int
    HPXNEST  True                                                                  str
    CHECKSUM 9HDaDFDY9FDaAFDW                                                      str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  0                                                                     str  data unit checksum updated 2022-03-13T17:03:18
    ======== ===================================================================== ==== ==============================================

Empty HDU.

HDU1
----

EXTNAME = B_WAVELENGTH

The wavelength vector for the spectra

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2751             int
    CHECKSUM fCA2iB32fBA2fB32 str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  979185614        str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2751]

HDU2
----

EXTNAME = B_MODEL

The best fit model in the B arm of the instrument.
This HDU contains as many rows as many there are rows in
the rvtab table. They also match one-to-one in terms of order.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2751             int
    NAXIS2   7                int
    CHECKSUM DTaaDRUTDRZYDRZY str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  2579859831       str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2751x7]

HDU3
----

EXTNAME = R_WAVELENGTH

The wavelength vector for the R arm of the instrument

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2326             int
    CHECKSUM fLCriLCofLCofLCo str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  456732359        str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2326]

HDU4
----

EXTNAME = R_MODEL

The best fit model in the R arm of the instrument.
This HDU contains as many rows as many there are rows in
the rvtab table. They also match one-to-one in terms of order.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2326             int
    NAXIS2   7                int
    CHECKSUM 3DbXABZW3BbWABZW str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  3703740820       str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2326x7]

HDU5
----

EXTNAME = Z_WAVELENGTH

The wavelength vector of the Z arm of the instrument

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2881             int
    CHECKSUM QiJBSZGAQfGAQZGA str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  3106662670       str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2881]

HDU6
----

EXTNAME = Z_MODEL

The best fit model in the Z arm of the instrument.
This HDU contains as many rows as many there are rows in
the rvtab table. They also match one-to-one in terms of order.

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   2881             int
    NAXIS2   7                int
    CHECKSUM daGBfY99daGAdY97 str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  1748435426       str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

Data: FITS image [float64, 2881x7]

HDU7
----

EXTNAME = FIBERMAP

The FIBERMAP targeting table for the objects. The same and in the same order as
in RVTAB

Required Header Keywords
~~~~~~~~~~~~~~~~~~~~~~~~

.. collapse:: Required Header Keywords Table

    .. rst-class:: keywords

    ======== ================ ==== ==============================================
    KEY      Example Value    Type Comment
    ======== ================ ==== ==============================================
    NAXIS1   341              int  length of dimension 1
    NAXIS2   7                int  length of dimension 2
    CHECKSUM eMIggKIfeKIfeKIf str  HDU checksum updated 2022-03-13T17:03:18
    DATASUM  19021304         str  data unit checksum updated 2022-03-13T17:03:18
    ======== ================ ==== ==============================================

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

