# Space Radiation Dosimetry

Any and all data regarding the conditions under which an experiment is conducted may have bearing on how the data produced during the experiment are interpreted; these conditions, explicitly documented or not, are a part of the experiment design. Therefore, GeneLab is taking actions, where possible and policies and available resources permit, to collect and publish data on these conditions. We have grouped these conditions into the areas listed below.

Dosimetry techniques vary depending on the particular experiment environment. To date, most flight experiments have not employed "dedicated" dosimeters (i.e. dosimeters integrated into experiment platform housing). Therefore, doses to which study samples are exposed frequently must be interpolated and/or extrapolated from nearby dosimeters. Two qualities of radiation were considered: low-LET (photons and electrons) and high-LET (charged nuclei). Both passive (thermoluminescent dosimeters: TLD, or plastic nuclear track detectors: PNTD) and active (solid state, tissue equivalent proportional counters) have been used. For passive dosimeters, TLD are sensitive to low-LET charged particles (< 10 keV/μm) and PNTD to high-LET (> 10 keV/μm). Active dosimeters are sensitive to a wider range in LET and, depending on the detector, can provide time resolution, LET spectra and some particle identification. By integrating the dose from the time-resolved data over the duration of the experiment, the total absorbed dose can be calculated. Depending on the configuration of dosimeters in the vicinity of the samples, absorbed dose may be reported as averaged with other detectors, or individually.

Datasets in the GeneLab repository with samples flown in space have corresponding metadata which includes the exposure duration, and the average, minimum and maximum absorbed dose received, broken out into low LET and high LET charged particles (when LET resolution is available). The duration of the exposure is defined as the time a sample was in space and biologically active, i.e. when the sample has returned to Earth or when it is chemically fixed or frozen in space. It is important to note that the absorbed doses we provide in these metadata are an approximation, due to several factors. First, the sensitivity in charge and LET for each detector being used. For example, even though TLDs detect low-LET radiation, the detected dose also includes some contribution from charged nuclei depending on the charge and speed of the nuclei traversing the detector. Similarly, active detectors even if sensitive to specific energies and charges, can still have contributions to dose from low-LET particles and neutrons. Second, reported dosimetry does not take into account the shielding provided by the sample enclosure. For low energy or low-LET particles this material could have effects unique to each mission and experiment, modifying both the dose and radiation quality.

Abbreviations: LET = Linear Energy Transfer, TLD = Thermoluminescent Dosimeters, PNTD = Plastic Nuclear Track Detectors.

**STS (Space Shuttle) Radiation Dosimetry**\
For STS (Space Shuttle) experiments, three passive dosimeter packages were fixed in locations on the shuttle middeck, where biological samples were located.

**BION-M1 Radiation Dosimetry**\
Both passive and active dosimeters were used.

**Foton-M4 Radiation Dosimetry**\
Passive dosimeters were used.

**ISS Radiation Dosimetry**\
Both passive and active dosimeters were used.

### Environmental Data Application

The Environmental Data Application provides the capability to visualize telemetry and radiation data collected on the International Space Station and corresponding ground platforms during the Rodent Research missions. Telemetry data includes temperature, relative humidity, and CO2 levels. Radiation data includes galactic cosmic rays, South Atlantic Anomaly, accumulated radiation dose, and total radiation dose. The application allows users to view single missions, compare two missions, and view and download summary or full data tables. So, come check out the new [Environmental Data Application](https://visualization.osdr.nasa.gov/eda/) now!

### RadLab Portal and RadLab Data API

The RadLab Portal provides access to radiation telemetry data from multiple databases maintained by multiple space agencies. The Web interface provides the ability to query, visualize, inspect, and download data; for example, time series plots of readings from multiple radiation detectors, pairwise comparisons of detector readings, and geospatial visualizations of radiation dose and flux registered by the detectors. The demo version of RadLab contains the data obtained from four detectors included in the DORELI project (DOSTEL1, DOSTEL2, Lidal, REM, Italian Space Agency) and the data from three Liulin-5 detectors (Bulgarian Academy of Sciences). All seven detectors are/were located on the International Space Station (ISS). The RadLab Data API enables data selection and retrieval at a programmatic level. Take a moment to explore the [RadLab Portal and Data API](https://visualization.osdr.nasa.gov/radlab/gui/data-overview/) now!
