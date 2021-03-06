Operator Hub Release Generator
===============================

Extracts CRDs and RBAC definitions from `all-in-one.yaml` and generates the files required to publish a new release to Operator Hub.

Usage
-----

- Edit `config.yaml` and update the values to match the new release
- Run the generator
- Inspect the generated files to make sure that they are correct

```shell
go run main.go --conf=config.yaml --out=out && tree out
```

IMPORTANT: The operator deployment spec is different from the spec in `all-in-one.yaml` and cannot be automatically extracted from it. Therefore, the deployment spec is hardcoded into the template and should be checked with each new release to ensure that it is still correct.
