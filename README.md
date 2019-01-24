# aws-get-session-token

CLI for accessing AWS with MFA and/or switching profiles

## Installation

`npm i aws-get-session-token -g`

## Usage

```
$ gst -p dev -t 123456

$ gst --help
Options:
  --profile, -p  Seed profile      [string] [default: "dev"]
  --token, -t    MFA token                          [string]
  --help         Show help                         [boolean]
```

## Configuration

Your aws credentials should be located at `~/.aws/credentials` per usual. Do not include a `[default]` profile because it will be generated by this utility. `mfa_arn` is the arn of the mfa device that is registered with your IAM user.

```
[dev]
aws_access_key_id=ZZZZZZZZZZZZZZZZZZZZZZ
aws_secret_access_key=zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz
mfa_arn=arn:aws:iam::123456789012:mfa/my-user
```

Now, when you invoke the aws-sdk, it defaults to using the session you last started.

Inspired by: [vividbytes/awsmfa](https://github.com/vividbytes/awsmfa) and many others
