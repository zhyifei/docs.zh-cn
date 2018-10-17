---
title: 强命名和.NET 库
description: 强命名的.NET 库的最佳实践建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372800"
---
# <a name="strong-naming"></a>强命名

强命名是指使用一个密钥，并生成程序集签名[强名称程序集](../../framework/app-domains/strong-named-assemblies.md)。 强名称的程序集时，它将创建唯一的标识基于名称和程序集版本号，并有助于防止程序集冲突。

强命名的缺点是，Windows 上的.NET Framework 使严格加载的程序集具有强名称程序集后。 一个强名称的程序集引用必须与引用的程序集，强制开发人员的版本完全匹配[配置的绑定重定向](../../framework/configure-apps/redirect-assembly-versions.md)时使用的程序集：

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

当.NET 开发人员抱怨有关强命名时，什么它们通常抱怨是严格的程序集加载。 幸运的是，此问题是独立于.NET Framework。 .NET core、 Xamarin、 UWP 和大多数其他.NET 实现没有严格的程序集加载并删除强命名的主要缺点。

强命名的一个重要方面是它是迅速传播开： 强名称程序集可以唯一引用其他强名称程序集。 如果你的库不是强命名，您已经排除生成的应用程序或需要使用它的强命名的库的开发人员。

强命名的优点有：

1. 可以引用并使用其他强名称程序集的程序集。
2. 程序集可以存储在全局程序集缓存 (GAC) 中。
3. 可以与其他版本的程序集并行加载程序集。 使用插件体系结构的应用程序通常所需的并行程序集加载。

## <a name="create-strong-named-net-libraries"></a>创建的强命名的.NET 库

您应具有强名称开放源.NET 库。 大多数人可以使用它，以及严格的程序集加载仅影响.NET Framework，可确保强命名程序集。

> [!NOTE]
> 本指南是特定于公开分布式.NET 库，如.NET 库在 NuGet.org 上发布。强命名不要求由大多数.NET 应用程序，而且不应默认情况下完成。

**请考虑 ✔️**强命名库的程序集。

**请考虑 ✔️**签入到源代码管理系统使用到强名称的密钥。

> 公开可用的密钥可让开发人员可以修改并使用相同的密钥重新编译库源代码。

> [!IMPORTANT]
> 当需要加密的标识，则[Authenticode](/windows-hardware/drivers/install/authenticode)并[NuGet 包签名](/nuget/create-packages/sign-a-package)建议。 有关安全注意事项的信息不应使用强命名。

**请考虑 ✔️**递增上仅主版本更改，以帮助用户减少绑定重定向和更新频率的程序集版本。

> 详细了解[版本控制和程序集版本](./versioning.md#assembly-version)。

**不这样做 ❌**添加、 删除或更改的强命名密钥。

> 修改程序集的强命名密钥更改程序集的标识，并将使用它的已编译的代码。 有关详细信息，请参阅[二进制的重大更改](./breaking-changes.md#binary-breaking-change)。

**不这样做 ❌**发布你的库的强名称的和非强命名版本。 例如，`Contoso.Api` 和 `Contoso.Api.StrongNamed`。

> 发布两个包分叉你开发人员生态系统。 此外，如果这两个包根据最终的应用程序开发人员可能会遇到类型名称冲突。 就.NET 而言它们是不同程序集中的不同类型。

>[!div class="step-by-step"]
[上一页](./cross-platform-targeting.md)
[下一页](./nuget.md)
