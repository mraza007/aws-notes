# IAM Authentication Methods.

- You can use `key-pair` access keys and its used for programmatic access especially CLI (You can't add MFA to this).
    + A combination of access key ID and secret key access.
    + this is used to make programmatic calls to aws when using the api. For example `boto`. Its also  used to access `AWS` using `CLI`.
    + you can _create_,_modify_,_view_ or _rotate_ access keys.
    + When created IAM returns the access key ID and secret access key.
    + The secret access key is returned only at the creation time and if lost new key must be created.
    + Make sure access keys and secret access keys are stored securely.
    + Users can be given access to change their own keys through IAM policy(Not from console).
    + You can disable user's access key which prevents it from being used for API calls.

- Simple username and password method to access the management console.
    + The password that user uses to sign in into `aws` web console 

- Some `AWS` services uses signing certificate.
    + `SSL/TLS` certificates that can be used to authenticate with some `AWS` services.
    + `AWS` recommends that you use `ACM`(AWS Certificate Manager) to provision manage and deploy your server certificates.
    + You can also use `IAM` only when you need to support `HTTPS` connections in a region that is not supported by `ACM`.
