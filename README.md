# CRUFT
CyanRip Unified File Tasks

CRUFT

## CyanRip Unified File Tasks

In honor of REACT for managing EAC, this is designed (I hope) for using cyanrip to do a unified file extraction focused on FLAC + metadata.

The cyanrip program is focused on extracting tracks to separate files, and an enhancement for single file extraction does not appear to be on the roadmap.
However, the advantage of CLI tools is that other CLI tools can be written to build upon them for specific use cases.
The intent is to build on the strengths of cyanrip (accuracy over speed) and then massage the output to match the unified file approach.

## Flow

Relies on very recent build of cyanrip (currently 0.9.4-rc2) to (eventually):
* Create a temporary working directory.
* Get disc info with the -I parameter.
* Create a cue sheet based on the result of that call.
* Extract CD data into separate files based on cyanrip's standard conventions.
* Merge those files into a single flac.
* Add metadata to the flac (cue sheet, cover image, etc.) that is lost in the merge process.
* Move the unified flac to users preferred location.
* Clean up the working directory (unless a keep option is specified).

