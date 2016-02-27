#### Backup and Install Atom Packages

Using the terminal, navigate to the `~/.atom` folder of your old install and store a list of all the installed packages in a file.

```
apm list --installed --bare > atom-packages.list
```

Next, create a zip package of all the necessary files

```
zip atom-settings.zip *.list *.cson *.coffee *.less *.json
```

_* If your shell complains about files not matching, try doing `unsetopt nomatch` before executing the command above. You can turn it back on later using `setopt nomatch`._

The following files are necessary to preserve your atom configuration
- `.cson`
- `.json`
- `.less`
- `.coffee`
- `atom-packages.list` (created earlier)

Now extract the created archive, `atom-settings.zip`, to the `~/.atom` folder on your new install, overwriting what's already in there. Keep a copy if you are reluctant in doing so.

Once the files are set, fire up the terminal and execute the following command

```
apm install --packages-file atom-packages.list
```
