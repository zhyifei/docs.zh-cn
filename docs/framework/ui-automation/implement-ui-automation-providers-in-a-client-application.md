---
title: 在客户端应用程序中实现 UI 自动化提供程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: a60253e62f814e9e3ea7ed4c5720e98e470d7f79
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043594"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="4ca7f-102">在客户端应用程序中实现 UI 自动化提供程序</span><span class="sxs-lookup"><span data-stu-id="4ca7f-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
> <span data-ttu-id="4ca7f-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4ca7f-104">有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4ca7f-105">本主题所包含的代码示例演示如何在应用程序中实现客户端 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="4ca7f-106">这种情况不常见。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-106">This is an uncommon scenario.</span></span> <span data-ttu-id="4ca7f-107">通常，UI 自动化客户端应用程序使用服务器端提供程序或驻留在 DLL 中的客户端提供程序。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ca7f-108">示例</span><span class="sxs-lookup"><span data-stu-id="4ca7f-108">Example</span></span>  
 <span data-ttu-id="4ca7f-109">下面的代码示例实现了一个简单的控制台窗口提供程序。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="4ca7f-110">此代码没有任何有用的功能，只是用于演示在客户端代码中设置提供程序以及使用 <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>注册此提供程序的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="4ca7f-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="4ca7f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca7f-111">See also</span></span>

- [<span data-ttu-id="4ca7f-112">UI 自动化提供程序概述</span><span class="sxs-lookup"><span data-stu-id="4ca7f-112">UI Automation Providers Overview</span></span>](ui-automation-providers-overview.md)
- [<span data-ttu-id="4ca7f-113">注册客户端提供程序程序集</span><span class="sxs-lookup"><span data-stu-id="4ca7f-113">Register a Client-Side Provider Assembly</span></span>](register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="4ca7f-114">创建客户端 UI 自动化提供程序</span><span class="sxs-lookup"><span data-stu-id="4ca7f-114">Create a Client-Side UI Automation Provider</span></span>](create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="4ca7f-115">客户端 UI 自动化提供程序的实现</span><span class="sxs-lookup"><span data-stu-id="4ca7f-115">Client-Side UI Automation Provider Implementation</span></span>](client-side-ui-automation-provider-implementation.md)
