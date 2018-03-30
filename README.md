# dotenv-export

Source & export `.env` into your shell.
Adds `export` statements to each line of a [dotenv] `.env` file, for defining
any variables therein in your shell.

## Install

```
npm i -g dotenv-export
```

## Use

```
source <(dotenv-export)
```

Or you can use a custom file name instead of the default `.env`, e.g., `.env.test`:

```
source <(dotenv-export .env.test)
```

### Multiline Support

To export multiline environment variables (as supported in the [`dotenv`](https://github.com/motdotla/dotenv#rules) package), use the literal characters `\n` in your variable:

```
PUBLIC_KEY="-----BEGIN RSA PUBLIC KEY-----\nMIICCgKCAgEAsTwK1Tireh3TVaJ66yUEAtLPP5tNuqwZW/kA64t7hgIRVKee1Wjb\nKLcHIJcAcioHJnqME96M+YRaj/xvlIFSwIbY1CRPgRkqH7kHs6mnrOIvmiRTPxSO\ntzydJxNB/13RsnuwPpG0MI/ZDNnSgj9sWVtJu4cgwoGpKzZctfhwZzJGBns9wChm\n2HewSTvUSRD2pgpheNS0kFkCsNmZgdhF2qaDfOXS6ie9+nKEms5/Y5/yA0EvAORh\nxnkw/JOkoOBoFX5DaZhQIAuqLmzmWvQqKxC1QTwgZh4zZw5hviBWRzh38uX/hIM7\nLe4lW0jxAIIMiPCcLnj5i9hqEYSRsIYIwHeLaBr4nnKcUMigq1Bttx7FbGgwqzRt\nicNQBXATk+xIpImCUYSq2ex1lJaClMxGERvUimHnl/bav+m7rLMW3hUmfdImMOGz\nTKYr7ozuFJOuT+Pj7L3b149DTFeYUO68G4PnuDisSMiYUf+qb/22T3repn7LbyY1\nOEryFfAsTsyPKG05FHXXWFLvOYtqfEq0CCVuUicDq+r2ULlewEvf/Y8PzLww21q2\nfdaiDonXFWtxGiL7SL4Hzos8VQi0T0bnDebO8/2mELi12OJivrxlNPZsYdOob8i/\nXjxHHzaebcsy1ccp3cUHP2/3WOAz35x1UdFvYwQ/Qjh9Ud1Yoe4+wskCAwEAAQ==\n-----END RSA PUBLIC KEY-----"
```

And run the following command to convert the `\n` characters to actual new lines:

```
source <(dotenv-export | sed 's/\\n/\n/g')
```

[dotenv]: https://github.com/motdotla/dotenv
