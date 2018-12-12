---
title: .NET Core 2.2 的新增功能
description: 了解 .NET Core 2.2 的新增功能。
dev_langs: 
  - "csharp"
  - "vb"
author: rpetrusha
ms.author: ronpet
ms.date: 12/04/2018
---
# .NET Core 2.2 的新增功能

.NET Core 2.2 包括应用程序部署，运行时服务的事件处理，Azure SQL数据库身份验证，JIT 编译器性能以及执行 Main 方法之前的代码注入方面的功能改进。

## 新的部署模式

从 .NET Core 2.2 开始，您可以部署 [framework-dependent 可执行文件](../deployloying/index.md#framework-dependent-executables-fde)，它们是 **.exe** 文件而不是 **.dll** 文件。 功能上类似于 framework-dependent 的部署，framework-dependent 的可执行文件（FDE）的运行仍然共享和依赖系统的 .NET Core 版本。 您的应用仅包含您的代码和其他任何第三方依赖项。 与 framework-dependent 部署不同，FDE 是特定于平台的。

这种新的部署模式具有构建可执行文件而不是库的独特优势，这意味着您可以直接运行应用程序而无需先调用 `dotnet`。

## 核心

**在运行时服务中处理事件**

您可能经常希望监视应用程序对运行时服务的使用，例如 GC，JIT 以及 ThreadPool，去了解它们如何影响您的应用程序。 在 Windows 系统上，这通常通过监视当前进程的 ETW 事件来完成。 虽然这种方法仍然有效，但如果您在低权限环境或 Linux 或 macOS 上运行，ETW 并不总是可以使用的。

从 .NET Core 2.2 开始，现在可以使用 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithtype> 类来消费 CoreCLR 的事件。 这些事件描述了诸如 GC，JIT，ThreadPool 和 interop 之类的运行时服务的行为。 这些是与 CoreCLR ETW 部分提供程序相同的事件。 这允许应用程序消费这些事件或使用一种传输机制将它们发送到遥测聚合服务。 您可以在以下代码示例中查看如何订阅事件：

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // 在创建事件源时调用
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // 观察.NET EventSource运行时并启用其所有事件
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // 写入事件时调用
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // 将事件的内容写入控制台
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```
此外，.NET Core 2.2 将以下两个属性添加到 <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> 类，以提供有关 ETW 事件的其他信息：

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## 数据

**使用 SqlConnection.AccessToken 属性对 Azure SQL 数据库进行 AAD 身份验证**

从.NET Core 2.2 开始，Azure Active Directory 发出的访问令牌可用于向 Azure SQL 数据库进行身份验证。 为了支持访问令牌，<xref:System.Data.SqlClient.SqlConnection.AccessToken> 属性已添加到 <xref:System.Data.SqlClient.SqlConnection> 类中。 要利用 AAD 身份验证，请下载 System.Data.SqlClient NuGet 包的 4.6 版本。 要使用此功能，您可以使用 [.NET 版本的 Active Directory 身份验证库](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) 获取访问令牌值，它包含在 [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet 包中。

## JIT 编译改进

**分层编译仍然是一个可选特性**

在.NET Core 2.1中，JIT 编译器实现了一种新的编译器技术 *分层编译* 作为可选功能。 分层编译的目标是提高性能。 JIT 编译器的一项重要任务是优化代码执行。 但是，编译器优化代码的时间可能比运行时执行未优化代码的时间要长。 分层编译在 JIT 编译中引入了两个阶段：

- A **第一层**， 尽可能快地生成代码。

- A **第二层**， 为那些经常执行的方法生成优化代码。 第二层编译是并行执行的，以提高性能。

有关分层编译可能带来的性能改进的信息，见 [Announcing .NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) .

在 .NET Core 2.2 Preview 2 中，默认情况下启用了分层编译。 但是，我们已经确定我们仍然没有准备好默认启用分层编译。 因此在 .NET Core 2.2 中，分层编译仍然是一个可选功能。 有关分层编译可选的信息，请参阅 [.NET Core 2.1 的新增功能](dotnet-core-2-1.md) 中的 [Jit 编译器改进](dotnet-core-2-1.md#jit-compiler-improvements)。

## 运行时

**在执行Main方法之前注入代码**

从 .NET Core 2.2 开始，您可以在运行应用程序的 Main 方法之前使用 startup hook 来注入代码。 startup hook 使 host 可以在部署应用程序后自定义应用程序的行为，而无需重新编译或更改应用程序。

我们希望托管服务提供商来定义自定义的配置和策略，包括可能影响主入口点的加载行为的设置，例如 <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> 的行为。 hook 可用于设置跟踪或注入遥测，设置回调以进行处理，或定义其他依赖于环境的行为。 Hook 与入口点是分开的，因此不需要修改用户代码。

参见 [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) 了解更多信息。

## 请参阅

* [.NET Core 的新增功能](index.md)
* [ASP.NET Core 2.2 的新增功能](/aspnet/core/release-notes/aspnetcore-2.2)  
* [EF Core 2.2 的新增功能](/ef/core/what-is-new/ef-core-2.2)  
