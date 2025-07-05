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

It is safe to ignore any filename that begins with an underscore.

### Notes

You may need my phone's passcode to use the [Microsoft Authenticator app](https://apps.apple.com/us/app/microsoft-authenticator/id983156458) for [Two Factor Authorization (2FA)](https://en.wikipedia.org/wiki/Multi-factor_authentication). This can be found in [Section 7](#section-7) in the [bootstrap document](#brownell-bootstrap).

## Our Financial Information, Account Numbers, and Passwords

Passwords related to finances are located in the KeePass file `Cathy and Dave's Passwords.kbdx` in the `Finances` folder. An overview of our financial information is available on [Monarch Money](https://app.monarchmoney.com/).

Contact information for our financial advisor is available in [Section 6](#section-6) in the [bootstrap document](#brownell-bootstrap).

## Computer Backup

All of our pictures, music, videos, tax returns, etc. are stored on the server located in our house and regularly backed up to [Amazon Storage](https://aws.amazon.com/s3/) using [custom software](https://github.com/davidbrownell/FileBackup).

Restoring a backup will take multiple hours to complete and require up to 1 terabyte to complete.

### Prerequisite Software

The following software must be downloaded installed to restore a backup.

| Name                                                               | Description                                                                                                                    | Name Used to Describe the Install Location in the This Document | Link                                                 |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- | ---------------------------------------------------- |
| [7-Zip](https://www.7-zip.org/)                                    | A tool that compresses and encrypts backup content.                                                                            | `<7-Zip install location>`                                      | https://www.7-zip.org                                |
| [FileBackup](https://github.com/davidbrownell/FileBackup/releases) | A tool that creates and restores backups.                                                                                      | `<FileBackup install location>`                                 | https://github.com/davidbrownell/FileBackup/releases |
| [S3 Browser](https://s3browser.com/)                               | A tool that makes it easier to transfer content from [AWS](https://aws.amazon.com/) (which is where the backup content lives). | N/A                                                             | https://s3browser.com                                |
| [Windows Terminal](https://github.com/microsoft/terminal/releases) | A tool that can be used to run command line applications.                                                                      | N/A                                                             | https://github.com/microsoft/terminal/releases       |

Installation files can be found in `./Files` at https://github.com/davidbrownell/LegacyInformation if the links above aren't working when you try to restore the backup.

### Prerequisite Setup

This process creates [symbolic links](https://en.wikipedia.org/wiki/Symbolic_link), where are disabled by default on Windows. Enabling [Developer Mode](https://learn.microsoft.com/en-us/windows/apps/get-started/developer-mode-features-and-debugging) will introduce changes that allow the creation of these links.

To enable developer mode on Windows:

A) Press the windows key and type "Developer Settings" or "Developer Mode" (which one you use will depend on your version of Windows).

B) Enable "Developer Mode" (the way that this is done will depend on your version of Windows).

### Restoring a Backup

#### 1) Register S3 Browser

S3 Browser performs MUCH better when registered. While not required, I highly recommend that you do this.

A) Launch KeyPass and search for "S3 Browser" in `<dropbox folder location>/Apps/KeePass/Dave's Passwords.kbdx`. Copy the key found in the "Notes" section.

B) Launch S3 Browser, select the "Help" menu item, select "Activate Pro Version", and paste the key copied in the previous step.

#### 2) Download Content using S3 Browser

A) Launch S3 Browser and create a new account using the information in [Section 5](#section-5) in the [bootstrap document](#brownell-bootstrap). Note that in S3 Browser, "Access Key ID" is the same as "username" and "Secret Access Key" is the same as "password".

B) After creating your account, you should see bucket names in the left pane of the application. S3 Browser seems to have a bug in that it will duplicate the names of the buckets the first time after logging in. To work around this, click the "Refresh" button and the duplicates should disappear.

C) Backed up content is stored on AWS Glacier. This is a less expensive storage option for content that is rarely read. So, you must request access to the content before it can be downloaded. To do this, select the `dbrownell-backup` bucket, right-click on the folder in the right-hand pane and select "Restore from Glacier". In the window that appears, specify that the restored files should be available for 5 days (or more if your download speeds are slow). Select the "Bulk" retrieval method and click the "Restore" button. The content should be available for download within 48 hours.

D) Once the content is available for download, click the "Download" button in S3 Browser. This will take a long time to complete. The download location on your local machine is referred to as `<S3 backup location>` in the remainder of this document.

#### 3) FileBackup (Dry Run)

In this step, we will decompress the downloaded content, look for errors, and view what will happen on a normal run. However, the backup content will not be restored on your machine yet.

A) Open a terminal by typing "Windows Key + R", typing `terminal --profile "Command Prompt"`, and clicking "OK".

B) Add 7-Zip to the path by typing `set PATH=%PATH%;%ProgramFiles%\7-Zip`. Note that you will see errors when running FileBackup if you forget to do this.

C) Navigate to `<FileBackup install location>` by typing `cd "<FileBackup install location>"`.

D) Identify a working directory to store temporary content. This will save time when running the next set of commands. This directory will be referred to as `<working directory>` in the remainder of this document.

E) Using KeePass, search for the Backup entry in `Dave's Passwords.kbdx`. This password will be referred to as `<encryption password>` in the remainder of this document.

F) Run `FileBackup offsite restore Backup "<S3 backup location>" --encryption-password "<encryption password>" --working-dir "<working directory>" --dry-run`

##### Errors

Hopefully, the dry run worked as expected. However, sometimes there can be problems restoring or transporting the content. If the previous command was not successful, you can append the argument `--continue-on-errors` to continue the restoration process even when errors are encountered. This means that some data will be lost, but hopefully there is more data that can be restored compared to the data lost. This command line flag will need to be included in all the FileBackup commands that follow.

`FileBackup offsite restore Backup "<S3 backup location>" --encryption-password "<encryption password>" --working-dir "<working directory>" --dry-run --continue-on-errors`

#### 4) FileBackup (Dry Run with Directory Substitutions)

When you ran FileBackup with `--dry-run`, it displayed all the files that would normally be restored (when the program is run without the `--dry-run` flag). You may have noticed that the files being restored will be written to the `C:\` and `D:\` drives. This is because those are the drives that were originally backed up on the server. However, you might not want to restore to those locations or even have a `D:\` drive to restore to. You can use the command line flag `--dir-substitution` to create mappings between the original file's location and where you would like to install to.

The syntax for directory substitutions looks a little bit scary because:

- Directory separators are specified as `/` rather than `\` as they normally are. This is because values as specified as [POSIX](https://en.wikipedia.org/wiki/POSIX) paths so FileBackup can run on Linux, MacOS, and Windows.

| Windows Path        | POSIX Path          |
| ------------------- | ------------------- |
| `C:\Dir1\Dir2`      | `C:/Dir1/Dir2`      |
| `D:\Dir3\File4.txt` | `D:/Dir3/File4.txt` |

- The ':' character has special meaning on the command line, so it must be [escaped](https://en.wikipedia.org/wiki/Escape_character) with a preceding `\` character.

| Value              | Escaped             |
| ------------------ | ------------------- |
| `one:two`          | `one\:two`          |
| `https://espn.com` | `https\://espn.com` |

Putting these rules together, a filename on Windows might looks like:

| Value               | Command Line         |
| ------------------- | -------------------- |
| `C:\Dir1\Dir2`      | `C\:/Dir1/Dir2`      |
| `D:\Dir3\File4.txt` | `D\:/Dir3/File4.txt` |

Let's say that you want to restore content to `C:\RestoredBackup`. To ensure that all files are restored to that location, you would provide the command line arguments that match this table:

| Original Location | Restored Location      | Command Line Argument                             |
| ----------------- | ---------------------- | ------------------------------------------------- |
| `C:\`             | `C:\RestoredBackup\C\` | `--dir-substitution "C\:/=C\:/RestoredBackup/C/"` |
| `D:\`             | `C:\RestoredBackup\D\` | `--dir-substitution "D\:/=C\:/RestoredBackup/D/"` |

resulting in:

`--dir-substitution "C\:/=C\:/RestoredBackup/C/" --dir-substitution "D\:/=C\:/RestoredBackup/D/"`

A) Run `FileBackup offset restore Backup "<S3 backup location>" --encryption-password "<encryption password>" --working-dir "<working directory>" <dir substitutions here> --dry-run`.

B) Inspect the dry run output to make sure that files will be written to the expected location.

#### 5) FileBackup (Restore Files)

Finally, we can restore the files! Run the command line in the previous section, removing the `--dry-run` command line argument.

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

### Section 7

`<phone code here>`
