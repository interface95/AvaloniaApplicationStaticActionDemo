# Avalonia Static Action Demo

This is an Avalonia UI desktop application that demonstrates AOT (Ahead-of-Time) compilation with SkiaSharp graphics.

## Features

- **Avalonia UI**: Modern cross-platform desktop UI framework
- **SkiaSharp**: High-performance 2D graphics library
- **AOT Compilation**: Native performance with .NET 9 AOT
- **Cross-platform**: Supports Windows, macOS, and Linux

## Build and Release

This project uses GitHub Actions for automated building and releasing:

### Workflow Features

- **Windows builds**: Windows x64 platform
- **AOT compilation**: Native performance with static linking
- **UPX compression**: Windows executables compressed with UPX (36% size reduction)
- **Automatic versioning**: Based on Git tags or commit count
- **Artifact generation**: Windows ZIP package
- **Release management**: Automatic GitHub releases with assets

### Triggering Builds

1. **Tag-based releases**: Push a tag starting with `v` (e.g., `v1.0.0`)
2. **Manual dispatch**: Use the "Actions" tab in GitHub to manually trigger builds

### Package Sources

The workflow automatically configures:
- **NuGet.org**: Standard .NET packages
- **Avalonia Nightly**: Latest Avalonia UI packages with AOT improvements
- **SkiaSharp**: High-performance 2D graphics library

## Development

### Prerequisites

- .NET 9.0 SDK
- Visual Studio 2022 or VS Code with C# extension

### Building Locally

```bash
# Restore dependencies
dotnet restore

# Build in Debug mode
dotnet build

# Run the application
dotnet run --project AvaloniaApplicationStaticActionDemo

# Publish AOT (example for Windows x64)
dotnet publish -r win-x64 -c Release -p:PublishAot=true --self-contained true
```

## Project Structure

```
AvaloniaApplicationStaticActionDemo/
├── .github/workflows/          # GitHub Actions workflows
│   └── build-and-publish-aot.yml
├── AvaloniaApplicationStaticActionDemo/
│   ├── App.axaml              # Application definition
│   ├── MainWindow.axaml       # Main window UI
│   ├── Program.cs             # Application entry point
│   └── AvaloniaApplicationStaticActionDemo.csproj
└── README.md
```

## Dependencies

- **Avalonia 12.0**: UI framework
- **SkiaSharp 3.119.0**: High-performance 2D graphics library
- **.NET 9.0**: Runtime and SDK

## License

This project is licensed under the MIT License.
