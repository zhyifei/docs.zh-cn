---
title: "缓解：ZipArchiveEntry.FullName 路径分隔符"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c9f271e10014d2f6fb04eb4279b068b7a191639f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="8ddd2-102">缓解：ZipArchiveEntry.FullName 路径分隔符</span><span class="sxs-lookup"><span data-stu-id="8ddd2-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="8ddd2-103">自定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的应用起，<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> 属性中使用的路径分隔符已从旧版 .NET Framework 中使用的反斜杠 ("\\") 更改为正斜杠 ("/")。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="8ddd2-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> 对象是通过调用 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName> 方法的重载之一进行创建。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8ddd2-105">影响</span><span class="sxs-lookup"><span data-stu-id="8ddd2-105">Impact</span></span>  
 <span data-ttu-id="8ddd2-106">该更改使 .NET 实现遵循 [.ZIP 文件格式规范](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)的 4.4.17.1 部分，还允许 .ZIP 存档在非 Windows 系统上进行解压缩。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="8ddd2-107">对于定位非 Windows 操作系统（如 Macintosh）上旧版 .NET Framework 的应用程序，解压缩其创建的 zip 文件无法保留目录结构。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="8ddd2-108">例如，在 Macintosh 上，应用程序创建一组文件，它们的文件名与目录路径相连，还与任何反斜杠 ("\\") 字符相连。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="8ddd2-109">因此，不会保留解压缩的文件的目录结构。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="8ddd2-110">对于在 Windows 操作系统上由 .NET Framework<xref:System.IO> 命名空间中的 API 解压缩的 .ZIP 文件，此更改造成的影响应该是最小的，因为这些 API 可以无缝地将正斜杠 ("/") 或反斜杠 ("\\") 处理为路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8ddd2-111">缓解操作</span><span class="sxs-lookup"><span data-stu-id="8ddd2-111">Mitigation</span></span>  
 <span data-ttu-id="8ddd2-112">如果不需要此行为，可以在应用程序配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加配置设置，从而选择禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="8ddd2-113">下面展示了 `<runtime>` 部分和选择禁用此行为的开关。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="8ddd2-114">此外，对于定位旧版 .NET Framework，但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更高版本上运行的应用程序，可以在应用程序配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加配置设置，从而选择启用此行为。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="8ddd2-115">下面展示了 `<runtime>` 部分和选择启用此行为的开关。</span><span class="sxs-lookup"><span data-stu-id="8ddd2-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ddd2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ddd2-116">See Also</span></span>  
 <span data-ttu-id="8ddd2-117">[重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md) </span><span class="sxs-lookup"><span data-stu-id="8ddd2-117">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md) </span></span>  
 [<span data-ttu-id="8ddd2-118">4.6.1 中的应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="8ddd2-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

