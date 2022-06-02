# pact-create-environment
Composite action to create a new environment for pact broker

**When would you use it?**

When you want to create new environment in pact broker using a github composite action

## Arguments

| Argument Name     | Required | Default | Description                                                                         | Allowed             |
|-------------------|----------|---------|-------------------------------------------------------------------------------------|---------------------|
| `name`            | True     | N/A     | The uniquely identifying name of the environment as used in deployment code         |                     |
| `display_name`    | True     | N/A     | The display name of the environment                                                 |                     |
| `is_production`   | False    | false   | Whether or not this environment is a production environment                         | **true**, **false** |
| `contact_name`    | False    | N/A     | The name of the team/person responsible for this environment                        |                     |
| `contact_email`   | False    | N/A     | The email address of the team/person responsible for this environment               |                     |
| `broker_base_url` | True     | N/A     | Pact_Broker/Pact_Flow  base url                                                     |                     |
| `broker_username` | False    | N/A     | Pact Broker basic auth username                                                     |                     |
| `broker_password` | False    | N/A     | Pact Broker basic auth password                                                     |                     |
| `broker_token`    | False    | N/A     | Pact Broker bearer token                                                            |                     |

## Example

### create new environment with all required parameters

```yaml
- uses: rajnavakotiikea/pact-create-environment@v1.0.1
  with:
    name: stage-env
    display_name: stage
    broker_token: pact_broker_token
    broker_base_url: pact_broker_url
```

### create new environment with all possible parameters

```yaml
- uses: rajnavakotiikea/pact-create-environment@v1.0.1
  with:
    name: stage-env
    display_name: stage
    is_production: false
    broker_token: pact_broker_token
    broker_base_url: pact_broker_url
    contact_name: foo
    contact_email: bar@foo.com
```