# Install

```
#kubens <mon>
helm upgrade -i  stresstest ./   -f myvalues.yaml  --debug --dry-run
kctl get cm oc-casc-bundle  -o yaml
```

# cb-ci-local

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

Local helm chart for additional configuration beyond remote cloudbees-ci helm chart

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| agents.cache.enable | bool | `false` | Cache for builds artifacts |
| agents.cache.storageClassName | string | `""` | Storage Class Name for PVC. Empty string will take the default one |
| agents.namespace | string | `"cbci-agents"` | Agents Namespace name |
| agents.policies | bool | `false` | Enable Limit Range and Resource Quoatas |
| controllers.loadTest.controllers | int | `0` | Number of Load Controllers for Performance Testing |
| controllers.policies | bool | `false` | Enable Limit Range and Resource Quoatas |
| operationCenter.casc.controllerBundleStorageSCM | string | `"https://github.com/carlosrodlop/cb-casc-controllers.git"` | Location of CloudBees Bundle Storage for Controller |
| operationCenter.credentials.github | object | `{"token":"ghp_xxxxExampleToken","user":"gh_ExampleUser"}` | Github Secret pair |
| operationCenter.credentials.github.token | string | `"ghp_xxxxExampleToken"` | Github Secret for token |
| operationCenter.credentials.github.user | string | `"gh_ExampleUser"` | Github Secret for user |
| operationCenter.credentials.jenkins.pass | string | `"thisIsSecret"` | Jenkins password |
| operationCenter.hostname | string | `"example.com"` | DNS zone (Eg: Route 53 in Hosted Zone in AWS) |
| operationCenter.ingress.class | string | `"alb"` | alb or nlb |
| operationCenter.protocol | string | `"https"` | http or https |
| operationCenter.subdomain | string | `"ci"` | Subdomain prefix used for all CloudBees CI applications (Operation Center and Controllers) |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
