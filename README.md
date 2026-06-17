# FlightData
Flight data (log files) for model validation

## Use as a Julia Artifact

This repository can be used as a [Julia artifact](https://pkgdocs.julialang.org/v1/artifacts/) for downloading flight data in packages or scripts.

### In a project

Add the following to your `Artifacts.toml`:

```toml
[flight_data]
git-tree-sha1 = "dc45f0e5f2ed023d7871660bdb1c9d29b9863edc"
lazy = true

    [[flight_data.download]]
    sha256 = "7c93b77c8fe3a3a78fb8268699c51d200e305736cedce6c01b67d21ef6f7d66e"
    url = "https://github.com/OpenSourceAWE/FlightData/releases/download/v0.1.0/flight_data.tar.gz"
```

Then access the data in Julia:

```julia
using LazyArtifacts
datadir = joinpath(artifact"flight_data", "flight_data")
# datadir now points to the extracted flight_data/ folder
```
List the files:
```
readdir(datadir)
```

### Manual download

The tarball can also be downloaded and extracted manually:

```bash
curl -LO https://github.com/OpenSourceAWE/FlightData/releases/download/v0.1.0/flight_data.tar.gz
tar -xzf flight_data.tar.gz
```
