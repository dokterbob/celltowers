# Cell tower database
Setup a PostGIS database with cell towers, sourced from [MLS](https://location.services.mozilla.com/downloads)
and [OpenCellID](http://opencellid.org/).

## Loading data
Loading this requires Postgres with PostGIS installe and [pgloader](http://pgloader.io/)
installed on the system.

### Mozilla Location Service
Make sure the compressed database is downloaded to the local machine, then run:

```sh
bunzip2 -c MLS-full-cell-export-<date>.csv.bz2 | pgloader mls.load
```

Note that this is not currently incremental and, hence, will drop all data on
every import.
