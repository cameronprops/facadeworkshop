# Façade Workshop

An early, touch-friendly prototype for tracing architectural façades from photographs and exploring their features on mobile or desktop.

## Run locally

Serve this folder over HTTP, for example:

```bash
python3 -m http.server 8000
```

Open http://localhost:8000 in a browser. A web server is needed for the installable app and service worker; opening the HTML file directly does not provide the complete offline experience.

## Current workflow

1. Load a photograph or choose **Load historic tenement**.
2. Use **Scan for features**, or draw rectangles and polygons manually.
3. Review suggested outlines; classify, rename, group, adjust, skip, or delete them.
4. Optionally save a confirmed example to the on-device feature library and search for similar features.
5. Assign projection values and inspect the conceptual 3D preview.
6. Save and reopen a project as JSON, or export flat outlines as DXF or SVG.

Suggested groups use approximate size and image appearance. Feature detection is based on image processing and example matching, not a trained machine-learning model. Results require review, and the app does not reliably detect every architectural feature.

## Offline use and privacy

After the application has been loaded online and its service worker has successfully cached the files, the app is designed to work offline on that browser and device. Browser storage may be cleared or evicted, so export project and feature-library backups. Photographs and processing remain in the browser; this static prototype has no upload server. Device-specific offline behavior and performance still need testing.

## Prototype limitations

The 3D view is an illustrative preview, not an editable CAD solid or print-ready model. Recess cuts, actual fillets and chamfers, curved façades, perspective correction, and STEP, STL, OBJ, FBX, 3MF, and PDF exports are not implemented. DXF exports 2D closed polylines with drawing units and group-derived layer names; photos, feature labels, depth, transitions and 3D geometry are not transferred. Numeric depths and scale must be supplied by the user. A single photo does not establish reliable depth.

## Reference image

The included sample is **[Exterior of tenement, New York City]**, Detroit Publishing Co., approximately 1900–1910, Library of Congress, LC-DIG-det-4a20846. The Library of Congress reports no known restrictions on publication. Its catalog does not specify the address.

[Library of Congress catalog record](https://www.loc.gov/pictures/item/2016812573/)

## BuilderCraft integration direction

Façade Workshop is a standalone app and is intended to work alongside BuilderCraft. The initial handoff is a 2D DXF drawing using closed polylines. An independent DXF reader checked example units, coordinates, layers and closure; import into BuilderCraft itself remains unverified. Both applications aim to support OBJ, DXF, STL, FBX, 3MF, STEP and SVG over time. Specific import/export paths must be implemented and tested before they are called supported.

## Project status

This repository captures the current experimental prototype. The existing hosted app and this GitHub repository are separate copies; changes do not automatically synchronize.
