# Layout Upgrader

This is the Sugar 7.0 Layout upgrader.

## How to use the script

You can ask for help anytime by simply run:
```bash
$ ./update-layouts -h
```

You can run this with directories:

```bash
$ ./update-layouts -d="directory/to/convert"
$ ./update-layouts --dir="directory/to/convert"
```

Or files only:

```bash
$ ./update-layouts -f="file/to/convert"
$ ./update-layouts --file="file/to/convert"
```

Both can be have multiple values:

```bash
$ ./update-layouts -d="directory1/to/convert" -d="directory2/to/convert"
$ ./update-layouts -f="file1/to/convert" -f="file2/to/convert"
```

Directories can have regex patterns (that will be used by glob):

```bash
$ ./update-layouts -d="directory1/*/to/*/convert"
```

For your convenience, you can keep the script out of the sugarcrm path and
combine the params above with the path of the [SugarCRM][SugarCRM] instance to
update:

```bash
$ ./update-layouts -p="path/to/sugarcrm" -d="directory/to/convert"
$ ./update-layouts --path="path/to/sugarcrm" -d="directory/to/convert"
```

In order to avoid mistakes, you can see how the script will handle the params
by passing the `--dry-run` option.

```bash
$ ./update-layouts -p="path/to/sugarcrm" -d="directory/to/convert" --dry-run
```

To see more output information from the script, you can use the `-v` option
(for verbose).

```bash
$ ./update-layouts -p="path/to/sugarcrm" -d="directory/to/convert" --dry-run -v
```

You can even be bold and run the script directly from github:

```bash
$ curl -sS https://raw.github.com/alias-mac/layout-upgrader/master/update-layouts | php -- --path="path/to/sugarcrm" -f="clients/base/layouts/activities/activities.php" --dry-run -v
```

### Removing .orig files in a burst

If you see that the script works great, you can delete the original files by
running a simple and fast command on your favorite shell:

```bash
$ find <path-to-sugarcrm> -name "*.php.orig" --delete
```

## Have fun!

## TODO

- Add the ability to run PSR-2 code fixer (optional param).
- Add the ability to prepend text (license headers) before the metadata

[SugarCRM]: http://www.sugarcrm.com/
