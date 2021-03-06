# spo site classic list

Lists classic sites of the given type

## Usage

```sh
spo site classic list [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`-t, --webTemplate [type]`|type of classic sites to list.
`-f, --filter [filter]`|filter to apply when retrieving sites
`-o, --output [output]`|Output type. `json|text`. Default `text`
`--includeOneDriveSites`|option to include OneDrive sites or not.
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

!!! important
    Before using this command, log in to a SharePoint Online tenant admin site, using the [spo login](../login.md) command.

## Remarks

To list classic sites, you have to first log in to a tenant admin site using the [spo login](../login.md) command, eg. `spo login https://contoso-admin.sharepoint.com`. If you are logged in to a different site and will try to list the available sites, you will get an error.

Using the `-t, --webTemplate` option you can specify which sites you want to retrieve. For example, to get sites with the `STS#0` as their web template, use `--webTemplate STS#0` as the option.

Using the `-f, --filter` option you can specify which sites you want to retrieve. For example, to get sites with _project_ in their URL, use `Url -like 'project'` as the filter.

Using the `--includeOneDriveSites`option you can specify whether you want to retrieve OneDrive sites or not. For example, to retrieve OneDrive sites, use `--includeOneDriveSites` as the option.

## Examples

List all classic sites in the currently connected tenant

```sh
spo site classic list
```

List all classic team sites in the currently connected tenant including OneDrive sites

```sh
spo site classic list --includeOneDriveSites
```

List all classic team sites in the currently connected tenant

```sh
spo site classic list --webTemplate STS#0
```

List all classic project sites that contain _project_ in the URL

```sh
spo site classic list --webTemplate PROJECTSITE#0 --filter "Url -like 'project'"
```