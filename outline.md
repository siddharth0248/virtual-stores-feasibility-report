1. Introduction / Executive Summary

Purpose of this report
Summary of recommendations and current state

2. The Case for Virtual Stores (Home Page / Landing Section)

2.1 What are virtual stores and what do they enable?
2.2 Vision: A single entrypoint for all NASA datasets
2.3 Benefits for data users
2.4 Benefits for data providers and NASA (cost savings, efficiency)

3. Technical Overview

3.1 Core concepts (Zarr, Icechunk, Kerchunk, chunk manifests)
3.2 Chunk manifest protocol (note: specification in progress)
3.3 GeoZarr and multiscales (adoption recommended)
3.4 Integration potential with EGIS (identified as a future priority)

4. Application of Virtual Store Technology to NASA Data

4.1 Mature implementations

Consistently gridded data → collection-level aggregated chunk manifests (PODAAC)


4.2 Developing implementations

Displacement data (ASF)
Ongoing/streaming data: appending via Icechunk vs. overwriting Kerchunk JSON
Non-uniform data: differing grids, compression schemes, L2/orbital swath data


4.3 Out of scope / not currently supported

(enumerate specific data types or patterns here)



5. Known Limitations

5.1 Language/ecosystem constraints: Icechunk is heavily Python- and Rust-centric
5.2 Early structural decisions have lasting performance consequences

Chunking and chunk manifest design trade-offs cannot simultaneously optimize for all use cases
Example: NISAR frame-level manifests optimize for per-frame loading but make cross-frame access difficult; dynamic aggregation of chunk manifests by use case is a desired future capability



6. Governance Decisions Required

6.1 Metadata placement standards

Collection-level metadata
Frame-level (or granule-level) metadata


6.2 Versioning and update policies for virtual layers
6.3 Ownership and stewardship of virtual store assets

7. Established Best Practices

7.1 Design files, chunks, and aggregated chunk manifests around typical use case patterns

Example: NISAR time series analysis → frame-oriented chunk manifest design


7.2 (Additional best practices as they are documented)

8. Recommendations Summary

Adopt GeoZarr and multiscales standards
Engage with the evolving chunk manifest protocol
Prioritize EGIS integration planning
Address governance gaps identified in Section 6


Appendices / Linked Resources

A. Onboarding Guide — Getting started with data virtualization
B. Virtualization Examples Library — Solved patterns across data types and use cases, serving as a resource for virtual layer producers