[![CI-CD](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/actions/workflows/ci-cd.yml/badge.svg?branch=main)](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/actions/workflows/ci-cd.yml) 
[![NuGet](https://img.shields.io/nuget/v/Our.Umbraco.HeadlessPreview)](https://www.nuget.org/packages/Our.Umbraco.HeadlessPreview)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/pulls)

# Our.Umbraco.HeadlessPreview

This package overrides the default Umbraco preview button and lets you configure an alternative preview url.

## Installation

Install the NuGet package to get started.

### Install the NuGet package

With .NET CLI

```bash
dotnet add package Our.Umbraco.HeadlessPreview --version <version>
```

Using the Package Manager

```bash
Install-Package Our.Umbraco.HeadlessPreview -Version <version>
```

## Configuration

The package can be configured using the `appsetings.json` file or using the UI which will save the configuration in the database.


| Setting               | Default value        | Description |
|----------             |-------------         |------ |
| `UseUmbracoHostnames` | `false`              | If set to true the domain from the `Culture and Hostnames` for the site is used as preview hostname.<br/><br/>If set to false the value from `StaticHostname` is used. |
| `StaticHostname`      | `''`                 | The hostname used for preview if `UseUmbracoHostnames` is set to false. |
| `RelativePath`        | `'api/preview'`      | The relative path to be used after the hostname. |
| `Secret`              | `''`                 | A secret value passed to the preview site for authentication. |

### UI

If you just have a single environment it's easy to just configure the plugin directly from the Umbraco Backoffice in the Settings section.

![Configuration](https://raw.githubusercontent.com/jesperweber/Our.Umbraco.HeadlessPreview/main/screenshots/Settings.png "Headless Preview Settings")

### appsettings.json
This is typically the preferred way if you have a multi environment setup as you can use environment specific settings.

``` json
"HeadlessPreview": {
    "UseUmbracoHostnames": false,
    "StaticHostname": "https://mysite.com",
    "RelativePath": "api/preview",
    "Secret": "mySecret"
}
```

## Changelog

See new features, fixes and breaking changes for each [Release](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/releases).


## Contributing

Pull requests are very welcome.  

Please fork this repository and make a PR when you are ready.  

Otherwise you are welcome to open an Issue in our [issue tracker](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/issues).


## License

Our.Umbraco.HeadlessPreview is [MIT licensed](https://github.com/jesperweber/Our.Umbraco.HeadlessPreview/blob/main/LICENSE)
