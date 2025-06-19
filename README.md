# Dave & Cathy's Legacy Information

If you are reading this, chances are pretty good that we are no longer around. First and foremost, we love you and can't wait to see you in Heaven!

If you are reading a hard-copy of this document, a version with working links is available at https://github.com/davidbrownell/LegacyInformation.

## Sensitive Information

To be safe, the instructions to [bootstrap](https://en.wikipedia.org/wiki/Bootstrapping) this process are here and sensitive information (such as passwords) can be found at:

```






```

The contents of this sensitive information will resemble [Brownell Bootstrap](#brownell-bootstrap) at the end of this document.

## Our Wills

A copy of our will is stored in the same location as the other [sensitive information](#sensitive-information).

## Our Passwords

All of our passwords and social security numbers are stored using a free application called [KeyPass](https://keepass.info/). The password files used by KeePass are stored on [Dropbox](https://www.dropbox.com/). You can access the passwords in those files using the instructions below.

1) Download and install [Dropbox](https://www.dropbox.com/). The username and password for this account are available in [Section 1](#section-1) of the [bootstrap document](#brownell-bootstrap). After you install Dropbox, it will begin to copy files to your computer. This location is referred to as `<dropbox folder location>` in the remainder of this document.

2) Download and install [KeyPass](https://keepass.info/). If KeePass is not available when reading this, you can find an installation file in `./Files/` at https://github.com/davidbrownell/LegacyInformation.

3) KeyPass files and passwords are available at these locations:

| File Name    | Dropbox Location                                                         | KeyPass Password                                                         |
| ------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Dave & Cathy | `<dropbox folder location>/Apps/KeePass/Cathy and Dave's Passwords.kbdx` | [Section 2](#section-2) in the [bootstrap document](#brownell-bootstrap) |
| Dave         | `<dropbox folder location>/Apps/KeePass/Dave's Passwords.kbdx`           | [Section 3](#section-3) in the [bootstrap document](#brownell-bootstrap) |
| Cathy        | `<dropbox folder location>/Apps/KeePass/Cathy's Passwords.kbdx`          | [Section 4](#section-4) in the [bootstrap document](#brownell-bootstrap) |

## Our Financial Information, Account Numbers, and Passwords
Passwords related to finances are located in the KeePass file `Cathy and Dave's Passwords.kbdx` in the `Finances` folder. An overview of our financial information is available on [Monarch Money](https://app.monarchmoney.com/).

Contact information for our financial advisor is available in [Section 6](#section-6) in the [bootstrap document](#brownell-bootstrap).

## Computer Backup

All of our pictures, music, videos, tax returns, etc. are stored on the server located in our house and regularly backed up to [Amazon Storage](https://aws.amazon.com/s3/) using [custom software](https://github.com/davidbrownell/FileBackup).

To restore a backup on a new computer:

1) Download and install [S3 Browser](https://s3browser.com/) (this is a Windows tool that makes it easier to work with Amazon Storage). If S3 Browser is not available when reading this, you can find an installation file in `./Files/` at https://github.com/davidbrownell/LegacyInformation.

2) Using S3 Browser, create a new account using the information in [Section 5](#section-5) in the [bootstrap-document](#brownell-bootstrap). Note that in S3 Browser, "Access Key ID" is the same as "username" and "Secret Access Key" is the same as "password".

3) In S3 Browser, download all of the data under the `Backup` directory to your local machine. This will take a long time to complete. The location on your local machine is referred to as `<S3 backup location>` in the remainder of this document.

4) Follow the instructions at https://github.com/davidbrownell/FileBackup to begin using FileBackup. The installed location will be referred to as `<FileBackup location>` in the remainder of this document.

5) Using KeePass, search for the `Backup` entry in `Dave's Passwords.kbdx`. This password will be referred to as `<encryption password>` in the remainder of this document.

6) Run this command line in `<FileBackup location>` to restore all of the backed up information:

`uv run FileBackup offsite restore "<S3 backup location>" --dir-substitution D\:=C\: --encryption-password <encryption password>`

## Brownell Bootstrap

(The following is an example of the contents described in [Sensitive Information](#sensitive-information))

### Section 1
username: `<username here>`
password: `<password here>`

### Section 2
`<something here>`

### Section 3
`<something here>`

### Section 4
`<something here>`

### Section 5
username: `<username here>`
password: `<password here>`

### Section 6
`<name, email, phone, address here>`
