---
title: 如何：跨应用程序会话保持和还原应用程序范围的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: c64b13717a427bf7ad8f9cab0a450162ad0c6cde
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204695"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="61b38-102">如何：跨应用程序会话保持和还原应用程序范围的属性</span><span class="sxs-lookup"><span data-stu-id="61b38-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="61b38-103">此示例演示如何保留应用程序关闭时，以及如何还原应用程序作用域属性时应用程序下一步是启动应用程序作用域属性。</span><span class="sxs-lookup"><span data-stu-id="61b38-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61b38-104">示例</span><span class="sxs-lookup"><span data-stu-id="61b38-104">Example</span></span>  
 <span data-ttu-id="61b38-105">应用程序仍然存在，应用程序作用域属性，并将其还原从独立存储。</span><span class="sxs-lookup"><span data-stu-id="61b38-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="61b38-106">独立的存储是由没有文件访问权限的应用程序可以安全使用的受保护的存储区域。</span><span class="sxs-lookup"><span data-stu-id="61b38-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="61b38-107">*App.xaml*文件定义`App_Startup`为处理程序方法<xref:System.Windows.Application.Startup?displayProperty=nameWithType>事件，并且`App_Exit`为处理程序方法<xref:System.Windows.Application.Exit?displayProperty=nameWithType>事件，如突出显示的行的第一个示例中所示。</span><span class="sxs-lookup"><span data-stu-id="61b38-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="61b38-108">第二个示例显示了部分*App.xaml.cs*并*App.xaml.vb*突出显示的代码文件`App_Startup`方法，后者将恢复应用程序作用域属性和`App_Exit`方法，将保存应用程序范围的属性。</span><span class="sxs-lookup"><span data-stu-id="61b38-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>
 
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
 
