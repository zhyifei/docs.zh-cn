---
title: 缓解：自定义 IMessageFilter.PreFilterMessage 实现
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb3283d089f4e823db051cd7ee450a1df6b866e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096935"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="22b50-102">缓解：自定义 IMessageFilter.PreFilterMessage 实现</span><span class="sxs-lookup"><span data-stu-id="22b50-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>
<span data-ttu-id="22b50-103">在面向从 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 开始的 .NET Framework 版本的 Windows 窗体应用中，如果 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 实现可以满足以下要求，那么在调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 方法时，自定义实现 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 可以安全地筛选消息：</span><span class="sxs-lookup"><span data-stu-id="22b50-103">In Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>  
  
-   <span data-ttu-id="22b50-104">执行下列一项或两项操作：</span><span class="sxs-lookup"><span data-stu-id="22b50-104">Does one or both of the following:</span></span>  
  
    -   <span data-ttu-id="22b50-105">通过调用 <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 方法添加消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="22b50-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>  
  
    -   <span data-ttu-id="22b50-106">通过调用 <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 方法，删除消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="22b50-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="22b50-107">方法。</span><span class="sxs-lookup"><span data-stu-id="22b50-107">method.</span></span>  
  
-   <span data-ttu-id="22b50-108">以及通过调用 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 方法抽取消息。</span><span class="sxs-lookup"><span data-stu-id="22b50-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="22b50-109">影响</span><span class="sxs-lookup"><span data-stu-id="22b50-109">Impact</span></span>  
 <span data-ttu-id="22b50-110">此更改仅影响面向开头为 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的 .NET Framework 版本的 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="22b50-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="22b50-111">对于面向以前版本的 .NET framework 的 Windows 窗体应用程序，在调用 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 方法时，此类实现在某些情况下会引发 <xref:System.IndexOutOfRangeException> 异常</span><span class="sxs-lookup"><span data-stu-id="22b50-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="22b50-112">缓解</span><span class="sxs-lookup"><span data-stu-id="22b50-112">Mitigation</span></span>  
 <span data-ttu-id="22b50-113">如果无需进行此更改，面向 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 或更高版本的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分来选择放弃更改：</span><span class="sxs-lookup"><span data-stu-id="22b50-113">If this change is undesirable, apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 <span data-ttu-id="22b50-114">此外，面向 .NET Framework 先前版本但在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 或更高版本下运行的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分，来选择实现此行为：</span><span class="sxs-lookup"><span data-stu-id="22b50-114">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22b50-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="22b50-115">See also</span></span>

- [<span data-ttu-id="22b50-116">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="22b50-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
