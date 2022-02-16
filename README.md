# ESW-Model-Files
Executive Software System ICD model files

The [observe-events](observe-events) directory contains templates for standard ESW observe events.
Note that these are defined here as "events" in order to show which fields are in the predefined
observe events. In subsystem model files, you only need to include the name of the observe events.

For example, to indicate that ALL of the possible observe events are published by a component,
you can add this to the publish-model.conf file:
```
  observeEvents = [
    ObserveStart
    ObserveEnd
    ExposureStart
    ExposureEnd
    ReadoutEnd
    ReadoutFailed
    DataWriteStart
    DataWriteEnd
    ExposureAborted
    PrepareStart

    // IRDetector specific
    IRDetectorExposureData
    IRDetectorExposureState

    // OpticalDetector specific
    OpticalDetectorExposureData
    OpticalDetectorExposureState

    // WFSDetector specific
    WfsDetectorExposureState
    PublishSuccess
    PublishFail

    // Sequencer specific
    PresetStart
    PresetEnd
    GuidestarAcqStart
    GuidestarAcqEnd
    ScitargetAcqStart
    ScitargetAcqEnd
    ObservationStart
    ObservationEnd
    ObservePaused
    ObserveResumed
    DowntimeStart

    // DMS specific
    MetadataAvailable
    ExposureAvailable
  ]
```

When the ICD software creates a PDF or web page for a component, the observe event names 
are replaced by the contents of the template events.

Based on 
_"ESW PDR DETAILED DESIGN DOCUMENT: Detectors, Observe Events and Metrics Detailed Design"_
(TMT.SFT.TEC.18.003.REL01.DRF04).
