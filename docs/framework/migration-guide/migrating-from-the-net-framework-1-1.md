---
title: 从 .NET Framework 1.1 迁移
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c683ce454e4db36367cb097371427d27dc4c555
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636352"
---
# <a name="migrating-from-the-net-framework-11"></a><span data-ttu-id="c7563-102">从 .NET Framework 1.1 迁移</span><span class="sxs-lookup"><span data-stu-id="c7563-102">Migrating from the .NET Framework 1.1</span></span>

[!INCLUDE[win7](../../../includes/win7-md.md)] <span data-ttu-id="c7563-103">及更高版本的 Windows 操作系统不支持 [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c7563-103">and later versions of the Windows operating system do not support the [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)].</span></span> <span data-ttu-id="c7563-104">因此，面向 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 的应用程序在未进行修改的情况下将不会在 [!INCLUDE[win7](../../../includes/win7-md.md)] 或更高版本的操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="c7563-104">As a result, applications that target the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] will not run without modification on [!INCLUDE[win7](../../../includes/win7-md.md)] or later operating system versions.</span></span> <span data-ttu-id="c7563-105">本主题介绍了在 [!INCLUDE[win7](../../../includes/win7-md.md)] 及更高版本的 Windows 操作系统控制下运行定位 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 的应用程序时需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="c7563-105">This topic discusses the steps required to run an application that targets the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] under [!INCLUDE[win7](../../../includes/win7-md.md)] and later versions of the Windows operating system.</span></span> <span data-ttu-id="c7563-106">有关 [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] 和 [!INCLUDE[win8](../../../includes/win8-md.md)] 的详细信息，请参阅[在 Windows 8 及更高版本上运行 .NET Framework 1.1 应用程序](../../../docs/framework/install/run-net-framework-1-1-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="c7563-106">For more information about the [!INCLUDE[net_v11_long](../../../includes/net-v11-long-md.md)] and [!INCLUDE[win8](../../../includes/win8-md.md)], see [Running .NET Framework 1.1 Apps on Windows 8 and later versions](../../../docs/framework/install/run-net-framework-1-1-apps.md).</span></span>

## <a name="retargeting-or-recompiling"></a><span data-ttu-id="c7563-107">重定目标或重新编译</span><span class="sxs-lookup"><span data-stu-id="c7563-107">Retargeting or Recompiling</span></span>

<span data-ttu-id="c7563-108">可通过两种方式让使用 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 编译的应用程序在 [!INCLUDE[win7](../../../includes/win7-md.md)] 或更高版本的 Windows 操作系统上运行：</span><span class="sxs-lookup"><span data-stu-id="c7563-108">There are two ways to get an application that was compiled using the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] to run on [!INCLUDE[win7](../../../includes/win7-md.md)] or a later Windows operating system:</span></span>

- <span data-ttu-id="c7563-109">你可以重定向应用程序以在 .NET Framework 4 及更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="c7563-109">You can retarget the application to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="c7563-110">重定向要求将 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素添加到应用程序的配置文件中，以允许它在 .NET Framework 4 及更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="c7563-110">Retargeting requires that you add a [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) element to the application's configuration file that allows it to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="c7563-111">此配置文件采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="c7563-111">Such a configuration file takes the following form:</span></span>

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- <span data-ttu-id="c7563-112">可以使用面向 .NET Framework 4 及更高版本的编译器重新编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7563-112">You can recompile the application with a compiler that targets the .NET Framework 4 or a later version.</span></span> <span data-ttu-id="c7563-113">如果你最初使用 Visual Studio 2003 开发和编译解决方案，则可在 Visual Studio 2010（也可能是更高版本）中打开它，然后使用“项目兼容性”对话框将该解决方案和项目文件从 Visual Studio 2003 使用的格式转换为 Microsoft 生成引擎 (MSBuild) 格式。</span><span class="sxs-lookup"><span data-stu-id="c7563-113">If you originally used Visual Studio 2003 to develop and compile your solution, you can open the solution in Visual Studio 2010 (and possibly later versions too) and use the **Project Compatibility** dialog box to convert the solution and project files from the formats used by Visual Studio 2003 to the Microsoft Build Engine (MSBuild) format.</span></span>

<span data-ttu-id="c7563-114">无论您是想重新编译应用程序还是重定应用程序的目标，都必须确定应用程序是否会受更高版本的 .NET Framework 中引入的任何更改的影响。</span><span class="sxs-lookup"><span data-stu-id="c7563-114">Regardless of whether you prefer to recompile or retarget your application, you must determine whether your application is affected by any changes introduced in later versions of the .NET Framework.</span></span> <span data-ttu-id="c7563-115">这些更改分为两类：</span><span class="sxs-lookup"><span data-stu-id="c7563-115">These changes are of two kinds:</span></span>

- <span data-ttu-id="c7563-116">[!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 和更高版本的 .NET Framework 之间存在的重大更改。</span><span class="sxs-lookup"><span data-stu-id="c7563-116">Breaking changes that occurred between the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] and later versions of the .NET Framework.</span></span>

- <span data-ttu-id="c7563-117">[!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 和更高版本的 .NET Framework 之间的已标记为弃用或过时的类型和类型成员。</span><span class="sxs-lookup"><span data-stu-id="c7563-117">Types and type members that have been marked as deprecated or obsolete between the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] and later versions of the .NET Framework.</span></span>

<span data-ttu-id="c7563-118">无论您重定应用程序的目标还是重新编译应用程序，都应查看 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)]之后发布的各个版本的 .NET Framework 的重大更改和已过时类型和成员。</span><span class="sxs-lookup"><span data-stu-id="c7563-118">Whether you retarget your application or recompile it, you should review both the breaking changes and the obsolete types and members for each version of the .NET Framework that was released after [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="c7563-119">重大更改</span><span class="sxs-lookup"><span data-stu-id="c7563-119">Breaking Changes</span></span>

<span data-ttu-id="c7563-120">发生重大更改时，解决方法可能对重定目标的应用程序和重新编译的应用程序都可用，这取决于具体的更改。</span><span class="sxs-lookup"><span data-stu-id="c7563-120">When a breaking change occurs, depending on the specific change, a workaround may be available both for retargeted and recompiled applications.</span></span> <span data-ttu-id="c7563-121">在某些情况下，可以在应用程序配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素中添加子元素，从而还原旧行为。</span><span class="sxs-lookup"><span data-stu-id="c7563-121">In some cases, you can add a child element to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) element of your application's configuration file to restore the previous behavior.</span></span> <span data-ttu-id="c7563-122">例如，下面的配置文件将还原 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] 中使用的字符串排序和比较行为，可以将该文件与重定目标的应用程序或重新编译的应用程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="c7563-122">For example, the following configuration file restores the string sorting and comparison behavior used in the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)] and can be used either with a retargeted or a recompiled application.</span></span>

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

<span data-ttu-id="c7563-123">但某些情况下，您可能必须修改源代码和重新编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7563-123">However, in some cases, you may have to modify your source code and recompile your application.</span></span>

<span data-ttu-id="c7563-124">若要评估重大更改对应用程序产生的影响，您必须查看以下更改列表：</span><span class="sxs-lookup"><span data-stu-id="c7563-124">To assess the impact of possible breaking changes on your application, you must review the following lists of changes:</span></span>

- <span data-ttu-id="c7563-125">[.NET Framework 2.0 中的重大更改](https://go.microsoft.com/fwlink/?LinkId=125263) 记录了 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] 中会影响面向 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)]的应用程序的更改。</span><span class="sxs-lookup"><span data-stu-id="c7563-125">[Breaking Changes in .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkId=125263) documents changes in [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] that can affect an application that targets [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].</span></span>

- <span data-ttu-id="c7563-126">[.NET Framework 3.5 SP1 中的更改](https://go.microsoft.com/fwlink/?LinkID=186989) 记录了 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 和 [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)]之间的更改。</span><span class="sxs-lookup"><span data-stu-id="c7563-126">[Changes in .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkID=186989) documents changes between the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] and the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)].</span></span>

- <span data-ttu-id="c7563-127">[.NET Framework 4 迁移问题](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)记录了 [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] 和 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 之间的更改。</span><span class="sxs-lookup"><span data-stu-id="c7563-127">[.NET Framework 4 Migration Issues](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md) documents changes between the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>

## <a name="obsolete-types-and-members"></a><span data-ttu-id="c7563-128">已过时的类型和成员</span><span class="sxs-lookup"><span data-stu-id="c7563-128">Obsolete Types and Members</span></span>

<span data-ttu-id="c7563-129">弃用的类型和成员对重定目标的应用程序和重新编译的应用程序产生的影响略有不同。</span><span class="sxs-lookup"><span data-stu-id="c7563-129">The impact of deprecated types and members is somewhat different for retargeted applications and recompiled applications.</span></span> <span data-ttu-id="c7563-130">使用已过时的类型和成员将不会影响重定目标的应用程序，除非已从其程序集中物理删除这些过时的类型或成员。</span><span class="sxs-lookup"><span data-stu-id="c7563-130">The use of obsolete types and members will not affect a retargeted application unless the obsolete type or member has been physically removed from its assembly.</span></span> <span data-ttu-id="c7563-131">重新编译使用过时的类型或成员的应用程序通常会产生编译器警告而不是编译器错误。</span><span class="sxs-lookup"><span data-stu-id="c7563-131">Recompiling an application that uses obsolete types or members usually produces a compiler warning rather than a compiler error.</span></span> <span data-ttu-id="c7563-132">但某些情况下会产生编译器错误，且无法成功编译使用过时的类型或成员的代码。</span><span class="sxs-lookup"><span data-stu-id="c7563-132">However, in some cases, it produces a compiler error, and code that uses the obsolete type or member does not compile successfully.</span></span> <span data-ttu-id="c7563-133">在此情况下，你必须先重新编写调用过时的类型或成员的源代码，然后再重新编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7563-133">In this case, you must rewrite the source code that calls the obsolete type or member before you recompile your application.</span></span> <span data-ttu-id="c7563-134">若要详细了解已过时类型和成员，请参阅[类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)。</span><span class="sxs-lookup"><span data-stu-id="c7563-134">For more information about obsolete types and members, see [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md).</span></span>

<span data-ttu-id="c7563-135">若要评估自发布 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] 后弃用的类型和成员的影响，请参阅[类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)。</span><span class="sxs-lookup"><span data-stu-id="c7563-135">To assess the impact of types and members that have been deprecated since the release of the [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], see [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md).</span></span> <span data-ttu-id="c7563-136">查看 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)]、[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 和 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 的过时类型和成员的列表。</span><span class="sxs-lookup"><span data-stu-id="c7563-136">Review the lists of obsolete types and member for the [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)], the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], and the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].</span></span>
