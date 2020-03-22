# Ubuntu PPAs

This repository contains PPAs for Kowainik:

* [Kowainik PPAs](https://launchpad.net/~kowainik)

## Working with PPAs

This section contains description of the PPA workflow: from installing
packages to preparing releases. All examples are given using the
`hit-on` package.

### How to install package?

```shell
sudo add-apt-repository --update ppa:kowainik/hit-on
sudo apt install hit-on
```

### How to prepare a new version of an existing PPA?

1. Enter the `hit-on` directory.
2. Copy binary of a new version to `bin/`.
3. Add new entry in the `debian/changelog` file.
   > TODO: probably some other files needs to be changed, to be clarified later
4. Build package:
    ```shell
    debuild -S
    ```
5. Step directory up.
6. Upload a new version to PPA using a command like:
    ```shell
    dput ppa:kowainik/hit-on hit-on_0.1.0.0_source.changes
    ```
