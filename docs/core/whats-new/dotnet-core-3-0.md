---
title: .NET Core 3.0 的新增功能
description: 了解 .NET Core 3.0 的新增功能。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 3ca833031eb8bb0f43a334f833f2e0075842d57d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156665"
---
# <a name="whats-new-in-net-core-30-preview-1"></a>.NET Core 3.0（预览版 1）的新增功能

本文介绍 .NET Core 3.0（预览版 1）的新增功能。 最大的增强功能之一是对 Windows 桌面应用程序（仅限 Windows）的支持。 通过利用名为“Windows 桌面”的 .NET Core 3.0 组件，可以移植 Windows 窗体 Windows Presentation Foundation (WPF) 应用程序。 为清楚起见，Windows 桌面组件仅在 Windows 上受支持。 有关详细信息，请参阅下面的 [Window 桌面](#windows-desktop)一节。

.NET Core 3.0 添加了对 C#8.0 的支持。

在 Windows、Mac 和 Linux 上立即[下载并开始使用 .NET Core 3 预览版 1](https://aka.ms/netcore3download)。 有关版本的完整详细信息，请参阅 [.NET Core 3 预览版 1 发行说明](https://aka.ms/netcore3releasenotes)。

有关详细信息，请参阅 [.NET Core 3.0 预览版 1 公告](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)。

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 实现 .NET Standard 2.1。

## <a name="default-executables"></a>默认可执行文件

.NET Core 不会默认生成可执行文件。 对于使用全局安装的 .NET Core 版本的应用程序而言，这是一项新功能。 到目前为止，仅[自包含部署](../deploying/index.md#self-contained-deployments-scd)拥有可执行文件。

在 `dotnet build` 或 `dotnet publish` 期间，将创建一个假设与你使用的 SDK 的环境和平台相匹配的可执行文件。 和其他本机可执行文件一样，可以使用这些可执行文件执行相同操作，例如：

* 可以双击可执行文件。
* 可以直接从命令提示符启用应用程序，如 Windows 上的 `myapp.exe`，以及 Linux 和 macOS 上的 `./myapp`。

> [!NOTE]
> 为特定运行时指定 `dotnet publish -r` 或 `dotnet build -r` 参数，因为不支持其他运行时环境。

## <a name="build-copies-dependencies"></a>生成副本依赖项

`dotnet build` 现将应用程序的 NuGet 依赖项从 NuGet 缓存复制到生成输出文件夹。 此前，依赖项仅作为 `dotnet publish` 的一部分复制。 

有些操作，比如链接和 razor 页面发布仍需要发布。


## <a name="local-dotnet-tools"></a>本地 dotnet 工具

虽然 .NET Core 2.1 支持全局工具，.NET Core 3.0 现在使用本地工具。 本地工具类似于全局工具，但与磁盘上的特定位置相关联。 这支持每个项目和每个存储库工具。 本地安装的任何工具都不可在全局范围使用。

本地工具依赖于当前目录中的清单文件名称 `dotnet-tools.json`。 此清单文件定义即将推出的工具。 通过在存储库的根目录中创建此清单文件，可确保克隆代码的任何人都可以恢复和使用所需的工具，以便成功使用代码。

当本地工具清单文件可用，请使用以下命令在本地自动下载和安装这些工具：

```console
dotnet tool restore
```

使用以下命令运行本地工具：

```console
dotnet tool run <tool-command-name>
```

调用本地工具时，dotnet 将搜索目录结构清单。 找到工具清单文件时，将在其中搜索请求的工具。 如果找到工具，它包含在 NuGet 全局包位置查找工具所需的信息。 

如果在清单中找到工具，但没有缓存，用户将收到一个错误。 将在预览版 1 后改进此消息，以请求用户运行 `dotnet tool restore`。

要向目录添加本地工具，需要首先创建工具清单文件。 在预览版 1 之后，我们将提供机制创建工具清单文件，如 dotnet 新模板。 对于预览版 1，必须创建名为 `dotnet-tools.json` 的文件，同时包含以下内容：

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

一旦创建清单，可以使用以下命令向其添加本地工具：

```console
dotnet tool install <toolPackageId>
```

此命令安装最新版本的工具，除非指定其他版本。  即使已自动选择最新版本，工具版本也会写入工具清单文件，以便恢复或运行正确版本的工具。

工具清单文件旨在允许手动编辑，你可能会执行此操作来更新使用存储库所需的版本。

下面是 `dotnet-tools.json` 示例文件：

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

要从工具清单文件中删除工具，请运行以下命令：

```console
dotnet tool uninstall <toolPackageId>
```

对于全局工具和本地工具，需要一个兼容的运行时版本。 目前，NuGet.org 上的许多工具都面向 .NET Core Runtime 2.1。 要在全局范围或本地安装这些工具，仍需要安装 [NET Core 2.1 运行时](https://dotnet.microsoft.com/download/dotnet-core/2.1)。

有关详细信息，请参阅[本地工具的早期预览文档](https://github.com/dotnet/cli/issues/10288)。

## <a name="windows-desktop"></a>Windows 桌面

从 .NET Core 3.0 预览版 1 开始，可以使用 WPF 和 Windows 窗体来生成 Windows 桌面应用程序。 这些框架还支持通过 [XAML 岛](/windows/uwp/xaml-platform/xaml-host-controls)从 Windows UI XAML 库 (WinUI) 使用新式控件和 Fluent 样式。

Windows 桌面部件是 Windows .NET Core 3.0 SDK 的一部分。

可以使用以下 `dotnet` 命令创建新的 WPF 或 Windows 窗体应用：

```console
dotnet new wpf
dotnet new winforms
```

还可以在 Visual Studio 2019 预览版 1 中打开、启用和调试 .NET Core 3.0 WPF 和 Windows 窗体项目。 目前可以在 Visual Studio 2017 15.9 中打开这些项目，然而，它并不是受支持的方案（而且需要[启用预览](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)）。

新项目与现有的 .NET Core 项目相同，其中有一些附加内容。 下面是基本 .NET Core 控制台项目与基本 Windows 窗体以及 WPF 项目之间的比较。

在 .NET Core 控制台项目中，该项目使用 `Microsoft.NET.Sdk` SDK 并通过 `netcoreapp3.0` 目标框架在 .NET Core 3.0 上声明依赖项。 要创建 Windows Desktop 应用，请使用 `Microsoft.NET.Sdk.WindowsDesktop` SDK 并选择要使用的 UI 框架：

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

若要选择 Windows 窗体而不是 WPF，请设置 `UseWindowsForms` 而不是 `UseWPF`：

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

如果应用同时使用这两个框架，则 `UseWPF` 和 `UseWindowsForms` 可以同时设置为 `true`，例如，当 Windows 窗体对话框托管 WPF 控件。

请在 [dotnet/winforms](https://github.com/dotnet/winforms/issues)、[dotnet/wpf](https://github.com/dotnet/wpf/issues) 和 [dotnet/core](https://github.com/dotnet/core/issues) 存储库上共享反馈。

## <a name="fast-built-in-json-support"></a>快速内置的 JSON 支持

`System.Text.Json.Utf8JsonReader` 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。 `Utf8JsonReader` 是一种基本的低级类型，可用于构建自定义分析器和反序列化程序。 使用新的 `Utf8JsonReader` 读取 JSON 有效负载要比使用 [Json.NET](https://www.newtonsoft.com/json) 的读取器快 2 倍。 在需要将 JSON 令牌实现为 (UTF-16) 字符串之前，它不会进行分配。

此新 API 将包含以下部件：

* 在预览版 1 中：JSON 读取器（顺序访问）
* 接下来推出：JSON 编写器、DOM（随机访问）、poco 序列化程序、poco 反序列化程序

下面是基本的 `Utf8JsonReader` 读取器循环，可以作为起点：

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

.NET 生态系统依赖于 [Json.NET](https://www.newtonsoft.com/json) 和其他常用的 JSON 库，它们仍是很好的选择。 JSON.NET 使用 .NET 字符串作为其基本数据类型，它实际上是 UTF-16。 

在 .NET Core 2.1 和 3.0 中，我们添加了新的 API，基于使用 `Span<T>` 和 UTF-8 字符串，可以编写需要更少内存的 JSON API (如 `Utf8JsonReader`)，同时更好地满足 Kestrel、ASP.NET Core Web 服务器等高吞吐量应用程序的需求。

## <a name="ranges-and-indices"></a>范围和索引

新 `Index` 类型可用于编制索引。 可以从从开头开始计数的 `int` 中创建一个类型，也可以使用从末尾开始计数的前缀 `^` 运算符 (C#) 创建一个：

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

此外，还有 `Range` 类型，它包含两个 `Index` 值，一个用于开头一个用于结尾，可以使用 `x..y` 范围表达式 (C#) 进行编写。 然后可以使用 `Range` 进行索引以便生成一个切片：

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> 仅 [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) 支持 `Range` 和 `Index` 语法。

## <a name="async-streams"></a>异步流

`IAsyncEnumerable<T>` 类型是 `IEnumerable<T>` 的新异步版本。 该语言允许你在其中执行 `await foreach` 操作来使用这些元素，并对其执行 `yield return` 操作以生成元素。

下面的示例演示如何生成和使用异步流。 `foreach` 语句为异步语句，它本身使用 `yield return` 为调用方生成异步流。 此模式（使用 `yield return`）是生成异步流的建议模型。

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> .NET Core 3.0 预览版 1 当前存在有关 `await foreach` 的 bug。 请改用 `GetEnumerator` 和 `MoveNext` 来处理元素。 有关详细信息，请参见 [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268)。

除了能够 `await foreach`，还可以创建异步迭代器，例如，一个返回 `IAsyncEnumerable/IAsyncEnumerator` 的迭代器，可以在其中进行 `await` 和 `yield` 操作。 对于需要处理的对象，可以使用各种 BCL 类型（如 `Stream` 和 `Timer`）实现的 `IAsyncDisposable`。

> [!NOTE]
> 仅 [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) 支持 `await foreach` 语法。

## <a name="type-sequencereader"></a>类型：SequenceReader

在 .NET Core 3.0 中，已添加可用作 `ReadOnlySequence<T>` 读取器的 `System.Buffers.SequenceReader`。 这样可以对跨多个支持缓冲区的 `System.IO.Pipelines` 数据进行简单、高性能、低分配分析。 

以下示例将输入 `Sequence` 分解为有效的 `CR/LF` 分隔行：

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>类型：MetadataLoadContext

添加了 `MetadataLoadContext` 类型，该类型支持读取程序集元数据，而不会影响调用方的应用程序域。 程序集作为数据读取，包括为与当前运行时环境不同的体系结构和平台构建的程序集。 `MetadataLoadContext` 与 <xref:System.Reflection.Assembly.ReflectionOnlyLoad*> 重叠，后者仅在 .NET Framework 中可用。

[System.Reflection.MetadataLoadContext 包](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) 现已推出 `MetdataLoadContext`。 它是一个 .NET Standard 2.0 包。

`MetadataLoadContext` 公开的 API 类似于 <xref:System.Runtime.Loader.AssemblyLoadContext> 类型，但不是基于该类型。 与 <xref:System.Runtime.Loader.AssemblyLoadContext> 非常相似，`MetadataLoadContext` 支持在一个独立的程序集加载范围内加载程序集。 `MetdataLoadContext` API 返回 <xref:System.Reflection.Assembly> 对象，支持使用熟悉的反射 API。 不允许以执行为导向的 API，如 [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127)，并将引发 InvalidOperationException。

下面的示例演示如何在实现给定接口的程序集中找到具体类型：

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

`MetadataLoadContext` 场景包括设计时功能、生成时工具和运行时启动功能，这些功能需要将一组程序集作为数据进行检查，并在执行检查后释放所有文件锁和内存。

`MetadataLoadContext` 有一个解析程序类传递给其构造函数。 解析程序的工作是在给定 `AssemblyName` 条件下加载 `Assembly`。 解析程序类派生自抽象 `MetadataAssemblyResolver` 类。 `PathAssemblyResolver` 提供了基于路径场景的解析程序的实现。

[MetadataLoadContext 测试](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests)演示了许多用例。 [程序集测试](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs)是一个很好的起点。

## <a name="tls-13--openssl-111-on-linux"></a>Linux 上的 TLS 1.3 和 OpenSSL 1.1.1

.NET Core 现在可以在给定环境中使用 [OpenSSL 1.1.1 中的 TLS 1.3 支持](https://www.openssl.org/blog/blog/2018/09/11/release111/)。 对于 [OpenSSL 团队](https://www.openssl.org/blog/blog/2018/09/11/release111/)来说，TLS 1.3 有许多好处：

* 由于减少了客户端和服务器之间所需的往返次数，从而提高了连接时间。

* 由于消除了各种过时和不安全的加密算法和加密了更多连接握手，从而提高了安全性。

.NET Core 3.0 预览版 1 能够利用 OpenSSL 1.1.1、OpenSSL 1.1.0 或 OpenSSL 1.0.2（无论在 Linux 系统上找到的最佳版本是什么）。  当 OpenSSL 1.1.1 可用时，SslStream 和 HttpClient 类型将在使用 `SslProtocols.None`（系统默认协议）时使用 TLS 1.3，假定客户端和服务器都支持 TLS 1.3。

下面的示例演示在 Ubuntu 18.10 上 .NET Core 3.0 预览版 1 如何连接到 <https://www.cloudflare.com>：

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows 和 macOS 尚不支持 TLS 1.3。 当支持可用时，.NET Core 3.0 将在这些操作系统上支持 TLS 1.3。

## <a name="cryptography"></a>密码

添加了对 AES-GCM 和 AES-CCM 密码的支持，通过 `System.Security.Cryptography.AesGcm` 和 `System.Security.Cryptography.AesCcm` 实现。 这些算法都是[使用关联数据的验证加密 (AEAD) 算法](https://en.wikipedia.org/wiki/Authenticated_encryption)，以及第一个添加到 .NET Core 的验证加密 (AE) 算法。

下面的代码演示了如何使用 AesGcm 密码加密和解密随机数据。

AesCcm 代码几乎完全相同（仅类变量名称不同）。

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>加密密钥导入/导出

.NET Core 3.0 预览版 1 支持从标准格式导入和导出非对称公钥和私钥，而不需要使用 X.509 证书。

所有密钥类型（RSA、DSA、ECDsa、ECDiffieHellman）都支持公钥的 X.509 SubjectPublicKeyInfo 格式，以及私钥的 PKCS#8 PrivateKeyInfo 和 PKCS#8 EncryptedPrivateKeyInfo 格式。 RSA 此外还支持 PKCS#1 RSAPublicKey 和 PKCS#1 RSAPrivateKey。 所有导出方法都生成 DER 编码的二进制数据，导入方法也是如此。 如果密钥以文本友好的 PEM 格式存储，调用方需要在调用导入方法之前对内容进行 base64 解码。

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

可以使用 `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` 类检查 PKCS#8 文件。

可以分别使用 `System.Security.Cryptography.Pkcs.Pkcs12Info` 和 `System.Security.Cryptography.Pkcs.Pkcs12Builder` 检查和操作 PFX/PKCS#12 文件。

## <a name="serialport-for-linux"></a>适用于 Linux 的 SerialPort

.NET Core 3.0 现在在 Linux 上支持 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>。

以前，.NET Core 只支持在 Windows 上使用 `SerialPort` 类型。

## <a name="more-bcl-improvements"></a>更多的 BCL 改进

.NET Core 2.1 中引入的 `Span<T>`、`Memory<T>` 和相关类型已在 .NET Core 3.0 中优化。 常见操作（例如跨越构造、切片、分析和格式化）现在可以更好地执行。 

此外，像 `String` 这样的类型已经看到了一些潜在的改进，使它们在与 `Dictionary<TKey, TValue>` 和其他集合一起用作键时更有效。 不需要更改代码就可以从这些改进中获益。

以下改进也是 .NET Core 3 预览版 1 中的新增功能：

* 内置于 HttpClient 的 Brotli 支持
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* 复杂算术运算符
* TCP 套接字 API 保持活动状态
* StringBuilder.GetChunks
* IPEndPoint 分析
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>分层编译

仅在 .NET Core 3.0 中默认启用[分层编译](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/)。 它是一项功能，使运行时能够更适应地使用实时 (JIT) 编译器，从而在启动时获得更好的性能，并最大限度地提高吞吐量。

此功能已作为一项可选功能添加到 [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/)，然后在 [.NET Core 2.2 预览版 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) 中默认启用。 随后，它在 .NET Core 2.2 版本中还原回可选功能。

## <a name="arm64-linux-support"></a>ARM64 Linux 支持

在此版本中，我们向 Linux 添加了对 ARM64 的支持。 有关上下文，我们在使用 .NET Core 2.1 的 Linux 和使用 .NET Core 2.2 的 Windows 中添加了对 ARM32 的支持。 ARM64 的主要用例是当前的 IoT 场景。

Alpine、Debian 和 Ubuntu [Docker 映像均适用于 .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/)。

有关详细信息，请查看 [.NET Core ARM64 状态](https://github.com/dotnet/announcements/issues/82)。

>[!NOTE]
> **ARM64** 尚未提供 Windows 支持。
