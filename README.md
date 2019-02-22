<p align="center">
    <img src="https://raw.githubusercontent.com/JamitLabs/ProjLintTemplates/stable/Logo.png"
      width=600>
</p>

<p align="center">
  <a href="#usage">Usage</a>
  • <a href="#contributing">Contributing</a>
  • <a href="#license">License</a>
</p>

# ProjLintTemplates

A maintained collection of templates for usage with [ProjLint](https://github.com/JamitLabs/ProjLint)'s `file_content_template` option.

## Usage

In your `.projlint.yml` add a new `file_content_template` section:

```yaml
  - file_content_template:
      matching:
        .swiftlint.yml:
          template_url: "https://raw.githubusercontent.com/JamitLabs/ProjLintTemplates/master/Community/App/ProjLint.stencil"
          parameters:
            rightholder: "Jamit Labs GmbH"
```

Note that any `parameters` will be replaced within the Stencil file. E.g. in the above example all `{{ rightholder }}` entries would be replaced. You can also use the `<:key:>` structure to reference any shared variables within your configuration file.

Here's a complete working example content for a `.projlint.yml` file:

```yaml
shared_variables:
  rightholder: Jamit Labs GmbH
  project_name: NewProjectTemplate

rules:
  - file_content_template:
      matching:
        .swiftlint.yml:
          template_url: "https://raw.githubusercontent.com/JamitLabs/ProjLintTemplates/master/JamitLabs/App/SwiftLint.stencil"
          parameters:
            rightholder: <:rightholder:>
        .projlint.yml:
          template_url: "https://raw.githubusercontent.com/JamitLabs/ProjLintTemplates/master/JamitLabs/App/ProjLint.stencil"
          parameters:
            rightholder: <:rightholder:>
            project_name: <:project_name:>
```

## Contributing

See the file [CONTRIBUTING.md](https://github.com/JamitLabs/ProjLint/blob/stable/CONTRIBUTING.md).

## License
This library is released under the [MIT License](http://opensource.org/licenses/MIT). See LICENSE for details.
