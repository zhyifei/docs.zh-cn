---
title: 如何： 获取所有 Windows 应用程序中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 476905899f5f7d573a16ba876c72f28ea34bbf9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="9e45b-102">如何： 获取所有 Windows 应用程序中</span><span class="sxs-lookup"><span data-stu-id="9e45b-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="9e45b-103">此示例演示如何获取所有<xref:System.Windows.Window>应用程序中的对象。</span><span class="sxs-lookup"><span data-stu-id="9e45b-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e45b-104">示例</span><span class="sxs-lookup"><span data-stu-id="9e45b-104">Example</span></span>  
 <span data-ttu-id="9e45b-105">每个实例化<xref:System.Windows.Window>对象时，是否可见，会自动添加到由管理的窗口引用的集合<xref:System.Windows.Application>，和从公开<xref:System.Windows.Application.Windows%2A>。</span><span class="sxs-lookup"><span data-stu-id="9e45b-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="9e45b-106">你可以枚举<xref:System.Windows.Application.Windows%2A>获取使用下面的代码的所有实例化的 windows:</span><span class="sxs-lookup"><span data-stu-id="9e45b-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
