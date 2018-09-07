---
title: 创建客户端 UI 自动化提供程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8763277052a15e7cde1a5b03e124551bc91328df
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097546"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="990c4-102">创建客户端 UI 自动化提供程序</span><span class="sxs-lookup"><span data-stu-id="990c4-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="990c4-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="990c4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="990c4-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="990c4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="990c4-105">本主题所包含的代码示例演示如何实现客户端 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="990c4-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="990c4-106">示例</span><span class="sxs-lookup"><span data-stu-id="990c4-106">Example</span></span>  
 <span data-ttu-id="990c4-107">下面的代码示例可内置于 [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] ，后者实现控制台窗口的十分简单的客户端提供程序。</span><span class="sxs-lookup"><span data-stu-id="990c4-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="990c4-108">此代码不具有任何有用的功能，只是用于演示设置提供程序程序集的基本步骤，该程序集可由 UI 自动化客户端应用程序进行注册。</span><span class="sxs-lookup"><span data-stu-id="990c4-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="990c4-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="990c4-109">See Also</span></span>  
 [<span data-ttu-id="990c4-110">UI 自动化提供程序概述</span><span class="sxs-lookup"><span data-stu-id="990c4-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="990c4-111">注册客户端提供程序程序集</span><span class="sxs-lookup"><span data-stu-id="990c4-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
