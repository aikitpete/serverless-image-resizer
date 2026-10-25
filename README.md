# serverless-image-resizer

AWS Lambda handler (Node.js), derived from the AWS Labs [serverless-image-resizing](https://github.com/awslabs/serverless-image-resizing) sample, that copies an object from one S3 bucket to another and answers with an HTTP 301 redirect to the copy.

`GET ?key=<name>.css|js` → read from `BUCKET_ORIGIN` → write to `BUCKET_DESTINATION` → `301` to `${URL}/<key>`

Configuration (environment variables): `BUCKET_ORIGIN`, `BUCKET_DESTINATION`, `URL`.

**Scope:** minimal handler for `.css` and `.js` assets. Image resizing (for example with `sharp`) is not implemented.

## Licence
Apache-2.0, see [LICENSE](LICENSE) and [NOTICE.md](NOTICE.md) (derived from Apache-2.0 licensed code).
