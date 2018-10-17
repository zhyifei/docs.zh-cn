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
# <a name="strong-naming"></a><span data-ttu-id="75da9-103">强命名</span><span class="sxs-lookup"><span data-stu-id="75da9-103">Strong naming</span></span>

<span data-ttu-id="75da9-104">强命名是指使用一个密钥，并生成程序集签名[强名称程序集](../../framework/app-domains/strong-named-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="75da9-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../../framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="75da9-105">强名称的程序集时，它将创建唯一的标识基于名称和程序集版本号，并有助于防止程序集冲突。</span><span class="sxs-lookup"><span data-stu-id="75da9-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="75da9-106">强命名的缺点是，Windows 上的.NET Framework 使严格加载的程序集具有强名称程序集后。</span><span class="sxs-lookup"><span data-stu-id="75da9-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="75da9-107">一个强名称的程序集引用必须与引用的程序集，强制开发人员的版本完全匹配[配置的绑定重定向](../../framework/configure-apps/redirect-assembly-versions.md)时使用的程序集：</span><span class="sxs-lookup"><span data-stu-id="75da9-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

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

<span data-ttu-id="75da9-108">当.NET 开发人员抱怨有关强命名时，什么它们通常抱怨是严格的程序集加载。</span><span class="sxs-lookup"><span data-stu-id="75da9-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="75da9-109">幸运的是，此问题是独立于.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="75da9-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="75da9-110">.NET core、 Xamarin、 UWP 和大多数其他.NET 实现没有严格的程序集加载并删除强命名的主要缺点。</span><span class="sxs-lookup"><span data-stu-id="75da9-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="75da9-111">强命名的一个重要方面是它是迅速传播开： 强名称程序集可以唯一引用其他强名称程序集。</span><span class="sxs-lookup"><span data-stu-id="75da9-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="75da9-112">如果你的库不是强命名，您已经排除生成的应用程序或需要使用它的强命名的库的开发人员。</span><span class="sxs-lookup"><span data-stu-id="75da9-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="75da9-113">强命名的优点有：</span><span class="sxs-lookup"><span data-stu-id="75da9-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="75da9-114">可以引用并使用其他强名称程序集的程序集。</span><span class="sxs-lookup"><span data-stu-id="75da9-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="75da9-115">程序集可以存储在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="75da9-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="75da9-116">可以与其他版本的程序集并行加载程序集。</span><span class="sxs-lookup"><span data-stu-id="75da9-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="75da9-117">使用插件体系结构的应用程序通常所需的并行程序集加载。</span><span class="sxs-lookup"><span data-stu-id="75da9-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="75da9-118">创建的强命名的.NET 库</span><span class="sxs-lookup"><span data-stu-id="75da9-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="75da9-119">您应具有强名称开放源.NET 库。</span><span class="sxs-lookup"><span data-stu-id="75da9-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="75da9-120">大多数人可以使用它，以及严格的程序集加载仅影响.NET Framework，可确保强命名程序集。</span><span class="sxs-lookup"><span data-stu-id="75da9-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="75da9-121">本指南是特定于公开分布式.NET 库，如.NET 库在 NuGet.org 上发布。强命名不要求由大多数.NET 应用程序，而且不应默认情况下完成。</span><span class="sxs-lookup"><span data-stu-id="75da9-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="75da9-122">**请考虑 ✔️**强命名库的程序集。</span><span class="sxs-lookup"><span data-stu-id="75da9-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="75da9-123">**请考虑 ✔️**签入到源代码管理系统使用到强名称的密钥。</span><span class="sxs-lookup"><span data-stu-id="75da9-123">**✔️ CONSIDER** checking in the key used to strong name into your source control system.</span></span>

> <span data-ttu-id="75da9-124">公开可用的密钥可让开发人员可以修改并使用相同的密钥重新编译库源代码。</span><span class="sxs-lookup"><span data-stu-id="75da9-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75da9-125">当需要加密的标识，则[Authenticode](/windows-hardware/drivers/install/authenticode)并[NuGet 包签名](/nuget/create-packages/sign-a-package)建议。</span><span class="sxs-lookup"><span data-stu-id="75da9-125">When a cryptographic identity is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="75da9-126">有关安全注意事项的信息不应使用强命名。</span><span class="sxs-lookup"><span data-stu-id="75da9-126">Strong naming should not be used for security considerations.</span></span>

<span data-ttu-id="75da9-127">**请考虑 ✔️**递增上仅主版本更改，以帮助用户减少绑定重定向和更新频率的程序集版本。</span><span class="sxs-lookup"><span data-stu-id="75da9-127">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="75da9-128">详细了解[版本控制和程序集版本](./versioning.md#assembly-version)。</span><span class="sxs-lookup"><span data-stu-id="75da9-128">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="75da9-129">**不这样做 ❌**添加、 删除或更改的强命名密钥。</span><span class="sxs-lookup"><span data-stu-id="75da9-129">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="75da9-130">修改程序集的强命名密钥更改程序集的标识，并将使用它的已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="75da9-130">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="75da9-131">有关详细信息，请参阅[二进制的重大更改](./breaking-changes.md#binary-breaking-change)。</span><span class="sxs-lookup"><span data-stu-id="75da9-131">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="75da9-132">**不这样做 ❌**发布你的库的强名称的和非强命名版本。</span><span class="sxs-lookup"><span data-stu-id="75da9-132">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="75da9-133">例如，`Contoso.Api` 和 `Contoso.Api.StrongNamed`。</span><span class="sxs-lookup"><span data-stu-id="75da9-133">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="75da9-134">发布两个包分叉你开发人员生态系统。</span><span class="sxs-lookup"><span data-stu-id="75da9-134">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="75da9-135">此外，如果这两个包根据最终的应用程序开发人员可能会遇到类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="75da9-135">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="75da9-136">就.NET 而言它们是不同程序集中的不同类型。</span><span class="sxs-lookup"><span data-stu-id="75da9-136">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="75da9-137">[上一页](./cross-platform-targeting.md)
[下一页](./nuget.md)</span><span class="sxs-lookup"><span data-stu-id="75da9-137">[Previous](./cross-platform-targeting.md)
[Next](./nuget.md)</span></span>
