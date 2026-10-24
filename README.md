# serverless-image-resizer

A small AWS Lambda handler, derived from the AWS Labs *serverless-image-resizing* sample, that copies an object from one S3 bucket to another and answers with an HTTP 301 redirect to the copy.

**Status:** unfinished experiment. As it stands the handler does **not resize images**: it only accepts `.css` and `.js` keys, copies the object and redirects. Resizing (for example with `sharp`) was never added, so it should not be used as an image resizer.

## What it does
`GET ?key=<name>.css|js` → read from `BUCKET_ORIGIN` → write to `BUCKET_DESTINATION` → `301` to `${URL}/<key>`.

Configuration (environment variables): `BUCKET_ORIGIN`, `BUCKET_DESTINATION`, `URL`.

## Known issues
- no image processing
- other extensions throw, and the content type of the copied object is set incorrectly
- no tests

## Licence
Derived from Apache-2.0 licensed code, see [NOTICE.md](NOTICE.md).
