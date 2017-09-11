---
title: "缓解：WPF 应用程序中的区域性和调度程序操作"
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
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="a0b8f-102">缓解：WPF 应用程序中的区域性和调度程序操作</span><span class="sxs-lookup"><span data-stu-id="a0b8f-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="a0b8f-103">在面向 .NET Framework 4.6 和 .NET Framework 4.6.1 的应用中，在 <xref:System.Windows.Threading.Dispatcher> 中执行的 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性更改，会在调度程序操作结束时丢失。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="a0b8f-104">同样，在调度程序操作外对 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 所做的更改在执行该操作时可能不会反映出来。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="a0b8f-105">这是因为 <xref:System.Threading.ExecutionContext> 中的更改会导致 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 存储在执行上下文中。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="a0b8f-106">WPF 调度程序操作存储用于启动操作的执行上下文，并在操作完成时还原以前的上下文。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="a0b8f-107">由于 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 现在属于该上下文，因此，在调度程序操作中对它们所做的更改在操作之外不会保留。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a0b8f-108">影响</span><span class="sxs-lookup"><span data-stu-id="a0b8f-108">Impact</span></span>  
 <span data-ttu-id="a0b8f-109">实际上，这意味着 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性的更改可能不会在 WPF UI 回调和 WPF 应用程序中的其他代码之间流动。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a0b8f-110">缓解操作</span><span class="sxs-lookup"><span data-stu-id="a0b8f-110">Mitigation</span></span>  
 <span data-ttu-id="a0b8f-111">受此更改影响的应用程序可以使用下面两种方法之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="a0b8f-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="a0b8f-112">通过将所需的 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 存储在字段中并签入所有 <xref:System.Windows.Threading.Dispatcher> 操作正文（包括用户界面事件回调处理程序）设置正确的 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="a0b8f-113">因为对 <xref:System.Threading.ExecutionContext> 的更改仅影响定位 .NET Framework 4.6 或 .NET Framework 4.6.1 的 WPF 应用程序，所以可通过定位 .NET Framework 4.5.2 或定位 .NET Framework 4.6.2 及更高版本来避免这一更改。</span><span class="sxs-lookup"><span data-stu-id="a0b8f-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b8f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b8f-114">See Also</span></span>  
 [<span data-ttu-id="a0b8f-115">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="a0b8f-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

