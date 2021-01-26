# STS (AWS Security Token)
- STS is a web service that enables you to request temporary, limited-priviledge crendentials for IAM users or for the users that you authenticate (federated users).

- By default `AWS` STS is available as global service and all AWS STS requests go to a single endpoint at  `https://sts.amazonaws.com`

- All regions are enabled by default for STS but can be disabled.

- The region in which temporary crendentials are requested must be enabled.