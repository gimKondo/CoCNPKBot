# CoCNPKBot
## Abstract
This is Slack bot backend for helping "Call of Cthulhu" keeper on Slack.
CoCNPK means "Call of Cthulhu Non Player Keep".
This bot is inspired by [CoCNonKP](https://github.com/cahlchang/CoCNonKP).

This bot responds to user's commands on Slack.
Commands include roll, showing status, checking SAN, etc...

## Development
### Requirements
- AWS CLI
- AWS SAM CLI
- [Docker](https://www.docker.com/community-edition)

### Initial construction
1. install requirement tools
2. create S3 bucket named "cocnpk-lambda"
3. set up aws cli configuration
   - default profile with several permissions

### make commands
`make` commands help you to deploy, test and etc.
You can run make on sam-app directory.

- test
  - execute unit tests
- package
  - check template.yaml and create packaged.yaml
- deploy
  - build and deploy
- clean
  - remove deployed package
- info
  - show endpoint URL
