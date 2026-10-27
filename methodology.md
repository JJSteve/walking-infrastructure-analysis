# Methods and quality checks

## Input definition

The original workflow used OpenStreetMap extracts covering the supplied study boundary. It selected separately mapped pedestrian linework using explicit highway and access rules. The source definition was provisional and did not claim to represent all real walking infrastructure.

## Spatial measurement

Geometry was measured in EPSG:3111. Exact overlapping linework was dissolved within matching layer, bridge and tunnel groups to avoid duplicate measurement while retaining relevant grade separation.

For each supplied destination polygon, fully covered simple lines contributed their full length. Other intersecting lines were clipped at the polygon boundary. Walking density was calculated as:

```text
walking density (m/km²) = intersected walking length (m) / polygon area (km²)
```

The neighbourhood context used supplied 1 km network polygons. The regional context used supplied 30-minute driving polygons. These are definitions of the destination areas, not walking distances.

## Record integration

Neighbourhood and regional records were linked using FacilityID, with agreement of the full destination identifier required before inheriting wave. The final output key combined participant identifier, wave and source.

Repeated keys with identical normalised geometry were collapsed. Conflicting geometry was retained in audit records but left missing in the canonical measurement table. Missing and conflicted measurements were not replaced with zero.

## Validation approach

The original project report records:

- 89 automated infrastructure tests and delivered-layer checks.
- 25 exposure, linkage and merge unit tests.
- End-to-end checks for checkpoint reuse and changed-input rejection.
- Checks of geometry hashes, original areas, density formulas and source/result hashes.
- 60 independent direct-intersection sample comparisons across walking and two cycling-definition alternatives.

These checks establish agreement between computational methods. They do not establish field accuracy, mapping completeness or historical infrastructure coverage.

## Limits of interpretation

The selected OpenStreetMap snapshot describes current mapped linework. It does not establish what infrastructure existed at the historical survey dates. Overlapping destination buffers cannot be added to estimate unique regional infrastructure. A measured zero means no selected mapped linework intersected a polygon, rather than proof that physical infrastructure is absent.

The case study omits participant-level records, precise destination polygons and restricted research outputs. It documents the approach and individual contribution without providing the original executable pipeline.
