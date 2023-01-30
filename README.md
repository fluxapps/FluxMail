# flux-mail-api

Mail Api for fetch or send mails

## Installation

### Native

#### Download

```dockerfile
RUN (mkdir -p /%path%/libs/flux-mail-api && cd /%path%/libs/flux-mail-api && wget -O - https://github.com/fluxfw/flux-mail-api/archive/refs/tags/%tag%.tar.gz | tar -xz --strip-components=1)
```

or

Download https://github.com/fluxfw/flux-mail-api/archive/refs/tags/%tag%.tar.gz and extract it to `/%path%/libs/flux-mail-api`

#### Load

```php
require_once __DIR__ . "/%path%/libs/flux-mail-api/autoload.php";
```

### Composer

```json
{
    "repositories": [
        {
            "type": "package",
            "package": {
                "name": "flux/flux-mail-api",
                "version": "%tag%",
                "dist": {
                    "url": "https://github.com/fluxfw/flux-mail-api/archive/refs/tags/%tag%.tar.gz",
                    "type": "tar"
                },
                "autoload": {
                    "files": [
                        "autoload.php"
                    ]
                }
            }
        }
    ],
    "require": {
        "flux/flux-mail-api": "*"
    }
}
```

## Environment variables

| Variable | Description | Default value |
| -------- | ----------- | ------------- |
| **FLUX_MAIL_API_MAIL_HOST** | Mail server host name | *-* |
| **FLUX_MAIL_API_MAIL_PORT** | Mail server port | *-* |
| **FLUX_MAIL_API_MAIL_TYPE** | Mail server type<br>imap, pop3 or nntp | *-* |
| **FLUX_MAIL_API_MAIL_USER_NAME** | Mail user name<br>Use *FLUX_MAIL_API_MAIL_USER_NAME_FILE* for docker secrets | *-* |
| **FLUX_MAIL_API_MAIL_PASSWORD** | Mail password<br>Use *FLUX_MAIL_API_MAIL_PASSWORD_FILE* for docker secrets | *-* |
| FLUX_MAIL_API_MAIL_ENCRYPTION_TYPE | Type to encrypt the connection to the server<br>ssl, tls or tls-auto | *-* |
| FLUX_MAIL_API_MAIL_BOX | Mail box path | INBOX |
| FLUX_MAIL_API_MAIL_MARK_AS_READ | Mark fetched mails as read | true |
| **FLUX_MAIL_API_SMTP_HOST** | SMTP server host name | *-* |
| **FLUX_MAIL_API_SMTP_PORT** | SMTP server port | *-* |
| **FLUX_MAIL_API_SMTP_FROM** | From email address | *-* |
| FLUX_MAIL_API_SMTP_FROM_NAME | From name | *-* |
| FLUX_MAIL_API_SMTP_ENCRYPTION_TYPE | Type to encrypt the connection to the server<br>ssl, tls or tls-auto | *-* |
| FLUX_MAIL_API_SMTP_USER_NAME | SMTP user name<br>Use *FLUX_MAIL_API_SMTP_USER_NAME_FILE* for docker secrets | *-* |
| FLUX_MAIL_API_SMTP_PASSWORD | SMTP password<br>Use *FLUX_MAIL_API_SMTP_PASSWORD_FILE* for docker secrets | *-* |
| FLUX_MAIL_API_SMTP_AUTH_TYPE | Type to authenticate on the server<br>PLAIN, LOGIN, CRAM-MD5 or XOAUTH2 | (Auto detect) |

Minimal variables required to set are **bold**

## Example

Look at [flux-mail-rest-api](https://github.com/fluxfw/flux-mail-rest-api)
