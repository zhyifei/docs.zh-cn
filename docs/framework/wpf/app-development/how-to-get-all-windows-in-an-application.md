---
title: 如何：在应用程序中获取所有窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947766"
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="aaa09-102">如何：在应用程序中获取所有窗口</span><span class="sxs-lookup"><span data-stu-id="aaa09-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="aaa09-103">此示例演示如何获取所有<xref:System.Windows.Window>应用程序中的对象。</span><span class="sxs-lookup"><span data-stu-id="aaa09-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa09-104">示例</span><span class="sxs-lookup"><span data-stu-id="aaa09-104">Example</span></span>  
 <span data-ttu-id="aaa09-105">每个实例化<xref:System.Windows.Window>对象是否可见或不是，自动添加到由管理的窗口中引用的集合<xref:System.Windows.Application>，并公开从<xref:System.Windows.Application.Windows%2A>。</span><span class="sxs-lookup"><span data-stu-id="aaa09-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="aaa09-106">您可以枚举<xref:System.Windows.Application.Windows%2A>若要获取所有实例化的窗口使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="aaa09-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
