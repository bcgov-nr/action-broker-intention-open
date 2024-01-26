# Broker Intention Open V1

This action opens an intention, so a service can access the Broker APIs. The ability to do the actions in the intention will be checked against business rules.

If you encounter an error, ensure that the Broker URL is correct, and your token is valid.

# Broker Documentation

Please refer to the [NR Broker Repository](https://github.com/bcgov-nr/nr-broker) for full usage details.

# Usage

<!-- start usage -->
```yaml
- uses: bcgov-nr/action-broker-intention-open@v1
  with:
    # The broker account JWT to use
    broker_jwt: ''

    # The path to the intention to send to the broker
    intention_path: ''

    # The broker url.
    # Default: 'https://nr-broker.apps.silver.devops.gov.bc.ca'
    broker_url: ''

    # Send quickstart parameter. Valid for intentions with a single action.
    # If true, the action will be started automatically.
    # Default: false
    quickstart: ''

    # Time to live (ttl) of the intention. The intention must be closed (and
    # all actions should finish) before the TTL expires. Set to explicitly send
    # the requested TTL (in seconds). If TTL is not set (and not sent), the
    # Broker's default is used.
    # Default: Use Broker default
    ttl: ''
```
<!-- end usage -->

# Output

This action outputs the intention/action tokens and intention ID as environment variables. The trace ids (for viewing in observability) will be output in the console.

### INTENTION_TOKEN

This is the token used to close the intention with the [action-broker-intention-close](https://github.com/bcgov-nr/action-broker-intention-close) action.

### INTENTION_ID

This is used to uniquely identify an intention. It can be used to view the intention in observability and refer to this intention in follow-on intentions.

### ACTION_TOKEN_\<ID\>

Each action within the intention has an 'id'. The capitalized 'id' property is appended to 'ACTION_TOKEN_' and set in the environment. This token can be used to start and end an action, retrieve secrets, and provision application access.

# License

The scripts and documentation in this project are released under the [Apache License](LICENSE)

