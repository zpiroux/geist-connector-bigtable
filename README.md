# GEIST bigtable Connector
<div>

[![Go Report Card](https://goreportcard.com/badge/github.com/zpiroux/geist-connector-bigtable)](https://goreportcard.com/report/github.com/zpiroux/geist-connector-bigtable)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=zpiroux_geist-connector-bigtable&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=zpiroux_geist-connector-bigtable)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=zpiroux_geist-connector-bigtable&metric=sqale_rating)](https://sonarcloud.io/summary/new_code?id=zpiroux_geist-connector-bigtable)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=zpiroux_geist-connector-bigtable&metric=reliability_rating)](https://sonarcloud.io/summary/new_code?id=zpiroux_geist-connector-bigtable)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=zpiroux_geist-connector-bigtable&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=zpiroux_geist-connector-bigtable)

</div>

GEIST Bigtable Connector enables Bigtable as a sink type in stream specs when using GEIST.

Note that this connector previously resided in the [geist-connector-gcp](https://github.com/zpiroux/geist-connector-gcp) repo, but was moved out to its own for improved maintainability and ease of use.

## Usage
See [GEIST core repo](https://github.com/zpiroux/geist) for general information.

Install with:
```sh
go get github.com/zpiroux/geist-connector-bigtable
```

### GEIST Integration

Register connector prior to starting up GEIST with (error handling omitted):
```go
import (
	"github.com/zpiroux/geist"
	"github.com/zpiroux/geist-connector-bigtable/gbigtable"
)

...
geistConfig := geist.NewConfig()

btConfig := &gbigtable.Config{ /* add config */ }

err = geistConfig.RegisterExtractorType(gbigtable.NewExtractorFactory(btConfig))
err = geistConfig.RegisterLoaderType(gbigtable.NewLoaderFactory(btConfig))

g, err := geist.New(ctx, geistConfig)
...
```

### Stream Spec Configuration

See stream spec examples [here](https://github.com/zpiroux/geist-connector-bigtable/gbigtable/test/specs).

## Contact
info @ zpiroux . com

## License
GEIST Bigtable Connector source code is available under the MIT License.