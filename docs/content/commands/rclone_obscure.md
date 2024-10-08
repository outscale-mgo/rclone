---
title: "rclone obscure"
description: "Obscure password for use in the rclone config file."
versionIntroduced: v1.36
# autogenerated - DO NOT EDIT, instead edit the source code in cmd/obscure/ and as part of making a release run "make commanddocs"
---
# rclone obscure

Obscure password for use in the rclone config file.

## Synopsis

In the rclone config file, human-readable passwords are
obscured. Obscuring them is done by encrypting them and writing them
out in base64. This is **not** a secure way of encrypting these
passwords as rclone can decrypt them - it is to prevent "eyedropping"
- namely someone seeing a password in the rclone config file by
accident.

Many equally important things (like access tokens) are not obscured in
the config file. However it is very hard to shoulder surf a 64
character hex token.

This command can also accept a password through STDIN instead of an
argument by passing a hyphen as an argument. This will use the first
line of STDIN as the password not including the trailing newline.

    echo "secretpassword" | rclone obscure -

If there is no data on STDIN to read, rclone obscure will default to
obfuscating the hyphen itself.

If you want to encrypt the config file then please use config file
encryption - see [rclone config](/commands/rclone_config/) for more
info.

```
rclone obscure password [flags]
```

## Options

```
  -h, --help   help for obscure
```

See the [global flags page](/flags/) for global options not listed here.

## See Also

* [rclone](/commands/rclone/)	 - Show help for rclone commands, flags and backends.

