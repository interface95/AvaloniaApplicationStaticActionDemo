# Avalonia 静态操作演示

这是一个 Avalonia UI 桌面应用程序，演示了使用 SkiaSharp 图形库的 AOT（提前编译）编译。

## 功能特性

- **Avalonia UI**: 现代化的跨平台桌面 UI 框架
- **SkiaSharp**: 高性能 2D 图形库
- **AOT 编译**: 使用 .NET 9 AOT 实现原生性能
- **跨平台**: 支持 Windows、macOS 和 Linux

## 构建和发布

本项目使用 GitHub Actions 进行自动化构建和发布：

### 工作流特性

- **Windows 构建**: Windows x64 平台
- **AOT 编译**: 真正的单文件静态链接，无需外部 DLL
- **UPX 压缩**: Windows 可执行文件使用 UPX 压缩（36% 大小减少）
- **自动版本管理**: 基于 Git 标签或提交计数
- **工件生成**: Windows ZIP 包
- **发布管理**: 自动 GitHub 发布和资源上传

### 触发构建

1. **标签发布**: 推送以 `v` 开头的标签（如 `v1.0.0`）
2. **手动触发**: 在 GitHub 的 "Actions" 标签页手动触发构建

### 包源配置

工作流自动配置：
- **NuGet.org**: 标准 .NET 包
- **Avalonia 夜间构建**: 最新的 Avalonia UI 包，包含 AOT 改进
- **SkiaSharp**: 高性能 2D 图形库

## 开发

### 前置要求

- .NET 9.0 SDK
- Visual Studio 2022 或带有 C# 扩展的 VS Code

### 本地构建

```bash
# 恢复依赖
dotnet restore

# Debug 模式构建
dotnet build

# 运行应用程序
dotnet run --project AvaloniaApplicationStaticActionDemo

# 发布 AOT（Windows x64 示例）
dotnet publish -r win-x64 -c Release -p:PublishAot=true --self-contained true
```

## 项目结构

```
AvaloniaApplicationStaticActionDemo/
├── .github/workflows/          # GitHub Actions 工作流
│   └── build-and-publish-aot.yml
├── AvaloniaApplicationStaticActionDemo/
│   ├── App.axaml              # 应用程序定义
│   ├── MainWindow.axaml       # 主窗口 UI
│   ├── Program.cs             # 应用程序入口点
│   └── AvaloniaApplicationStaticActionDemo.csproj
└── README.md
```

## 依赖项

- **Avalonia 12.0**: UI 框架
- **SkiaSharp 3.119.0**: 高性能 2D 图形库
- **.NET 9.0**: 运行时和 SDK

## 许可证

本项目采用 MIT 许可证。
