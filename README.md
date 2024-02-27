# Storing workflow data as artifacts

Artifacts allow you to share data between jobs in a workflow and store data once that workflow has completed.

## Description

### Artifacts

Files or collections of files produced during a workflow run that can be shared between jobs or downloaded after the run.

### Usage and billing

Artifacts are stored on GitHub for a default or custom retention period and use storage space that may affect billing.

### Uploading and downloading artifacts

You can use the upload-artifact and download-artifact actions to upload and download artifacts within a workflow run.

### Sharing data between jobs

You can use artifacts to pass data between jobs in a workflow, such as build output or test reports.

### Upload and Download Action

#### `actions/upload-artifact`

This action allows you to upload files or directories as artifacts during a workflow run. You can specify a name for the artifact, a path to the files or directories, and an optional retention period. Artifacts are useful for saving data after a job has completed, and sharing data with another job in the same workflow. For example, you can use artifacts to save your build and test output, code coverage reports, or production binaries.

```shell
- uses: actions/upload-artifact@v4
  with:
    # Name of the artifact to upload.
    # Optional. Default is 'artifact'
    name:

    # A file, directory or wildcard pattern that describes what to upload
    # Required.
    path:

    # The desired behavior if no files are found using the provided path.
    # Available Options:
    #   warn: Output a warning but do not fail the action
    #   error: Fail the action with an error message
    #   ignore: Do not output any warnings or errors, the action does not fail
    # Optional. Default is 'warn'
    if-no-files-found:

    # Duration after which artifact will expire in days. 0 means using default retention.
    # Minimum 1 day.
    # Maximum 90 days unless changed from the repository settings page.
    # Optional. Defaults to repository settings.
    retention-days:

    # The level of compression for Zlib to be applied to the artifact archive.
    # The value can range from 0 to 9.
    # For large files that are not easily compressed, a value of 0 is recommended for significantly faster uploads.
    # Optional. Default is '6'
    compression-level:

    # If true, an artifact with a matching name will be deleted before a new one is uploaded.
    # If false, the action will fail if an artifact for the given name already exists.
    # Does not fail if the artifact does not exist.
    # Optional. Default is 'false'
    overwrite:
```

#### `actions/download-artifact`

This action allows you to download artifacts that were previously uploaded in the same workflow run. You can specify a name for the artifact, or download all artifacts in the workflow run. You can also specify a path to the download directory. Artifacts are downloaded as zip files, and you can unzip them using the actions/cache@v2 action. Downloading artifacts is useful for accessing data from another job in the same workflow, or for viewing data after a workflow run has ended. For example, you can use artifacts to download your test results, build logs, or deployment packages.

## Demo

## Features

- feature:1
- feature:2

## Requirement

## Usage

## Installation

## References

- [@actions/upload-artifact](https://github.com/actions/upload-artifact)
- [@actions/download-artifact](https://github.com/actions/download-artifact)

## Licence

Released under the [MIT license](https://gist.githubusercontent.com/shinyay/56e54ee4c0e22db8211e05e70a63247e/raw/34c6fdd50d54aa8e23560c296424aeb61599aa71/LICENSE)

## Author

- github: <https://github.com/shinyay>
- twitter: <https://twitter.com/yanashin18618>
- mastodon: <https://mastodon.social/@yanashin>
