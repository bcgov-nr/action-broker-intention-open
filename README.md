# Broker Intention Open V1

This action opens an intention, so the service can access the broker.

If you encounter an error, ensure that the Broker URL is correct and your token is valid.

# Broker Documention

Please refer to the [NR Broker Repository](https://github.com/bcgov-nr/nr-broker) for full usage details.

# Usage

<!-- start usage -->
```yaml
- uses: bcgov-nr/action-broker-intention-close@v1
  with:
    # The intention to close.
    intention_token: ''

    # The broker url.
    # Default: 'https://nr-broker.apps.silver.devops.gov.bc.ca'
    persist-credentials: ''
```
<!-- end usage -->

# License

The scripts and documentation in this project are released under the [Apache License](LICENSE)

