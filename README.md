# Walking Infrastructure Analysis

A geospatial analytics course project at RMIT University supporting research on walking and cycling access around iMAP Melbourne destinations. My contribution focused on the infrastructure-processing pipeline, walking measurements and result integration.

**Author:** Joel Steve Santharoy  
**Completed:** September 2026  
**Tools:** Python, GeoPandas, Shapely, OpenStreetMap, GeoPackage and CSV

## Project purpose

The research team needed consistent measures of mapped walking infrastructure around supplied destinations to support later research into active travel in older adults. I processed infrastructure linework, measured the amount within supplied destination polygons and linked the results to destination and survey-wave records.

## My contribution

- Built a reusable workflow to extract, classify and clip OpenStreetMap walking and cycling features to the supplied study boundary.
- Calculated walking-network length and density within neighbourhood and regional destination polygons.
- Linked results using destination identifiers and composite keys, handled duplicate records and flagged conflicting geometry.
- Maintained audit records, documented measurement rules and checked computational consistency.

The three-person team shared the overall project. Cycling outputs and the broader demographic screening were separate team responsibilities.

## Evidence of scope and quality

| Measure | Documented project result |
| --- | --- |
| Candidate source features | 474,312 unique OpenStreetMap features |
| Result integration | 2,992 destination and survey-wave records |
| Infrastructure validation | 89 automated tests and delivered-layer checks |
| Exposure and linkage validation | 25 unit tests, plus separate end-to-end checks |
| Independent spatial comparisons | 60 direct-intersection comparisons across six runs |

These figures describe the submitted project evidence. They are not a claim of a new execution from this repository.

## Workflow

1. Extract current OpenStreetMap linework and apply explicit walking and cycling classification rules.
2. Clip the selected infrastructure to the supplied study boundary and use EPSG:3111 for measurement.
3. Intersect walking lines with the supplied 1 km network and 30-minute driving destination polygons.
4. Calculate total length in metres and density in metres per square kilometre.
5. Link destination and wave identifiers, collapse identical duplicates and flag conflicts.
6. Produce result tables, descriptive summaries and quality records.

## Interpretation

The measurements describe mapped infrastructure around destinations. They do not measure participants' travel distances. Baseline and follow-up destination groups use the same September 2026 infrastructure snapshot, so differences between them do not establish infrastructure change over time. Mapping completeness and physical conditions require separate verification.

## Repository contents

- [Methods and quality checks](methodology.md)
- This README provides an overview suitable for a professional portfolio.

This repository is a project case study. The original processing code, restricted participant polygons, coded result tables and full research package are not included, so the original analysis cannot be reproduced from these files.

## Source and attribution

The case study is based on my September 2026 technical contribution report and the group's final presentation. The infrastructure source snapshot was dated 17 September 2026. OpenStreetMap data is attributed to [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) under the Open Database Licence.

AI assisted with code generation, computation, automated checking and report preparation in the original project. AI also assisted with preparing this portfolio summary.
