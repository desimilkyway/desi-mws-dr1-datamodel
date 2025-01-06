=============
rvmod_spectra
=============

:Summary: This is the file containing the best fit models to spectra from rvspecfit
:Naming Convention: ``rvmod_spectra-main-backup-136.fits`` for a main survey, backup
		    program and healpixel 136
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
REF_CAT               char[2]              Reference catalog source for star: &#x27;T2&#x27; for Tycho-2, &#x27;G2&#x27; for Gaia DR2, &#x27;L2&#x27; for the SGA, empty otherwise
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
