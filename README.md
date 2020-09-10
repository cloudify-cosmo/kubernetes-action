Creates a Kubernetes environment.

# Prerequisites

The Cloudify Kubernetes Integration blueprint must be uploaded to Cloudify Manager, with the ID
`cloudify-kubernetes-1.0`.

## Environment Variables

This Action uses the Cloudify Profile environment variables described in the official
Cloudify documentation (see [More Information](#more-information) below).

# Inputs

(Certain commonly-used inputs are documented in our official website; see [More Information](#more-information) below)

| Name | Description
|------|------------
| `gcp-credentials-file` | Path to file containing GCP service account details
| `token` | Kubernetes API token
| `token-file` | Path to file containing an API token
| `master-host` | Hostname/IP of the main Kubernetes host
| `namespace` | Application's namespace
| `app-definition-file` | Path to Kubernetes application definition file
| `ca-cert-file` | Path, on Cloudify Manager, of a file to use as a CA trust store when connecting to the Kubernetes master host
| `ssl-cert-file` | Path, on Cloudify Manager, of a file to use as a certificate presented to the Kubernetes master host upon connection
| `ssl-key-file` | Path, on Cloudify Manager, of the private key file associated with the certificate specified by `ssl-cert-file`
| `skip-ssl-verification` | Whether to verify SSL connections
| `other-options-file` | YAML/JSON file containing additional Kubernetes options, to be passed along with the namespace
| `validate-status` | Whether to validate the status of the application upon creation
| `allow_node_redefinition` | Whether to allow Kubernetes node redefinition
| `debug` | Whether to generate debug logging of Kubernetes calls

# Notes

* Authentication to Kubernetes must be done in exactly one of the following methods:
  * Specifying `gcp-credentials-file`
  * Specifying `token` (this will usually be defined as a secret)
  * Specifying `token-file`

# More Information

Refer to [Cloudify CI/CD Integration](https://docs.cloudify.co/latest/working_with/integration/) for additional information about
Cloudify's integration with CI/CD tools.
