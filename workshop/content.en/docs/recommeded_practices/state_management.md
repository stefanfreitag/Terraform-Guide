+++
title = 'State Management'
type = 'docs'
+++

## Using AWS Services

When working in a team there is a general need for a remote state.
One of the common approaches is to store the state in an AWS S3 bucket.
In addition to the S3 bucket, a DynamoDB table is used to provide a locking mechanism.

Details on setting up those resources are below:

- The state should be encrypted.
- Versioning should be enabled.
