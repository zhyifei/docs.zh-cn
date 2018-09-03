---
title: 缓解：路径规范化
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa31641cc325f15b9afe677038deb33c57e77fd1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43388347"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="719ab-102">缓解：路径规范化</span><span class="sxs-lookup"><span data-stu-id="719ab-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="719ab-103">自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，.NET Framework 中的路径规范化已更改。</span><span class="sxs-lookup"><span data-stu-id="719ab-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="719ab-104">什么是路径规范化？</span><span class="sxs-lookup"><span data-stu-id="719ab-104">What is path normalization?</span></span>  
 <span data-ttu-id="719ab-105">路径规范化涉及修改用于标识路径或文件的字符串，使其与目标操作系统上的有效路径一致。</span><span class="sxs-lookup"><span data-stu-id="719ab-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="719ab-106">路径规范化通常涉及以下操作：</span><span class="sxs-lookup"><span data-stu-id="719ab-106">Normalization typically involves:</span></span>  
  
-   <span data-ttu-id="719ab-107">规范化处理组件和目录分隔符。</span><span class="sxs-lookup"><span data-stu-id="719ab-107">Canonicalizing component and directory separators.</span></span>  
  
-   <span data-ttu-id="719ab-108">将当前目录应用到相对路径。</span><span class="sxs-lookup"><span data-stu-id="719ab-108">Applying the current directory to a relative path.</span></span>  
  
-   <span data-ttu-id="719ab-109">评估路径中的相对目录 (`.`) 或父目录 (`..`)。</span><span class="sxs-lookup"><span data-stu-id="719ab-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
-   <span data-ttu-id="719ab-110">删减指定字符。</span><span class="sxs-lookup"><span data-stu-id="719ab-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="719ab-111">更改</span><span class="sxs-lookup"><span data-stu-id="719ab-111">The changes</span></span>  
 <span data-ttu-id="719ab-112">自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，路径规范化在以下几个方面进行了更改：</span><span class="sxs-lookup"><span data-stu-id="719ab-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="719ab-113">运行时在规范化处理路径时以操作系统的 [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) 函数为准。</span><span class="sxs-lookup"><span data-stu-id="719ab-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
-   <span data-ttu-id="719ab-114">路径规范化再也不用删减目录部分的末尾内容（如目录名称末尾的空格）。</span><span class="sxs-lookup"><span data-stu-id="719ab-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
-   <span data-ttu-id="719ab-115">支持完全信任形式的设备路径语法，包括 `\\.\` 和 `\\?\`（对于 mscorlib.dll 中的文件 I/O API）。</span><span class="sxs-lookup"><span data-stu-id="719ab-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
-   <span data-ttu-id="719ab-116">运行时不会验证设备语法路径。</span><span class="sxs-lookup"><span data-stu-id="719ab-116">The runtime does not validate device syntax paths.</span></span>  
  
-   <span data-ttu-id="719ab-117">支持使用设备语法来访问备用数据流。</span><span class="sxs-lookup"><span data-stu-id="719ab-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="719ab-118">影响</span><span class="sxs-lookup"><span data-stu-id="719ab-118">Impact</span></span>  
 <span data-ttu-id="719ab-119">对于定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本的应用程序，这些更改默认启用。</span><span class="sxs-lookup"><span data-stu-id="719ab-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="719ab-120">这些更改应该会提升性能，同时允许方法访问之前无法访问的路径。</span><span class="sxs-lookup"><span data-stu-id="719ab-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="719ab-121">定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本但在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本控制下运行的应用程序不会受此更改影响。</span><span class="sxs-lookup"><span data-stu-id="719ab-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="719ab-122">缓解</span><span class="sxs-lookup"><span data-stu-id="719ab-122">Mitigation</span></span>  
 <span data-ttu-id="719ab-123">对于定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本的应用程序，可以在应用程序配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的代码行，从而选择禁用此更改并使用旧版路径规范化：</span><span class="sxs-lookup"><span data-stu-id="719ab-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="719ab-124">对于定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本，但在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本控制下运行的应用程序，可以在应用程序配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的代码行，从而启用路径规范化更改：</span><span class="sxs-lookup"><span data-stu-id="719ab-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="719ab-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="719ab-125">See Also</span></span>  
 [<span data-ttu-id="719ab-126">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="719ab-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
