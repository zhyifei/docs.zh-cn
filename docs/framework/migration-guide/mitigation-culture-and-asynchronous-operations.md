---
title: "缓解：区域性和异步操作"
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
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="42af4-102">缓解：区域性和异步操作</span><span class="sxs-lookup"><span data-stu-id="42af4-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="42af4-103">对于面向 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 及更高版本的应用，<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 存储在线程的 <xref:System.Threading.ExecutionContext> 中，该线程在异步操作之间流动。</span><span class="sxs-lookup"><span data-stu-id="42af4-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="42af4-104">影响</span><span class="sxs-lookup"><span data-stu-id="42af4-104">Impact</span></span>  
 <span data-ttu-id="42af4-105">鉴于有此更改，对 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 的更改会反映在随后异步运行的任务中。</span><span class="sxs-lookup"><span data-stu-id="42af4-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="42af4-106">这与旧版 .NET Framework 的行为不同。旧版会在所有异步任务中将 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 重置为系统默认值。</span><span class="sxs-lookup"><span data-stu-id="42af4-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="42af4-107">缓解操作</span><span class="sxs-lookup"><span data-stu-id="42af4-107">Mitigation</span></span>  
 <span data-ttu-id="42af4-108">受此更改影响的应用程序可以通过下列两种方法之一解决此问题：</span><span class="sxs-lookup"><span data-stu-id="42af4-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="42af4-109">将所需 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性显式设置为异步任务中的第一项操作。</span><span class="sxs-lookup"><span data-stu-id="42af4-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="42af4-110">在应用程序配置文件中添加下面的 `AppContextSwitchOverrides` 元素，从而选择启用不流动 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 的旧行为：</span><span class="sxs-lookup"><span data-stu-id="42af4-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="42af4-111">以编程方式设置以下兼容性开关，从而选择启用不流动 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 的旧行为：</span><span class="sxs-lookup"><span data-stu-id="42af4-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="42af4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42af4-112">See Also</span></span>  
 [<span data-ttu-id="42af4-113">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="42af4-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

