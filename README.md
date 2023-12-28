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
    # The broker account JWT to use
    broker_jwt: ''

    # The path to the intention to send to the broker
    intention_path: ''

    # The broker url.
    # Default: 'https://nr-broker.apps.silver.devops.gov.bc.ca'
    broker_url: ''
```
<!-- end usage -->

# Output

This action outputs the intention and action tokens as environment variables.

### INTENTION_TOKEN

This is the token used to close the intention with the [action-broker-intention-close](https://github.com/bcgov-nr/action-broker-intention-close) action.

### ACTION_TOKEN_\<ID\>

Each action within the intention has an 'id'. The capitalized 'id' property is appended to 'ACTION_TOKEN_' and set in the environment. This token can be used to start and end an action, retrieve secrets and provision application access.

# License

The scripts and documentation in this project are released under the [Apache License](LICENSE)

