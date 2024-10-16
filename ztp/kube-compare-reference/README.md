# Reference (DU) validation with kube-compare

This directory `kube-compare-reference` contains all the references that can be used to validate a DU profile cluster. 

Please see [here](https://github.com/openshift/kube-compare/blob/main/docs/image-build.md) for the latest instruction on how to run this.

Required and Optional RDS are structured based on internal document "4.16 Telco Engineering RAN Reference Design Specification"

> [!CAUTION]
> We are in development and some APIs may change over time. There are a few TOODs that are mentioned in the metadata.yaml that may trigger unwanted diffs.

## Developer Notes

The reference should be kept in-sync with ../source-crs

The `make compare` target provided in this directory will compare the
reference, combining it with the examples in `default_value.yaml` and excluding
CRs listed in `compare_ignore`, and comparing the resulting reference-rendered
CRs with ../source-crs

If this check fails, either the source-crs or reference must be altered until
no differences are observed.

TODO: For now this is a manual activity, but it will soon be mandatory and
enforced by the github CI.
