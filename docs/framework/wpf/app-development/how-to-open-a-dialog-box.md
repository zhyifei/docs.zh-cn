---
title: "如何： 打开一个对话框"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="38e8f-102">如何： 打开一个对话框</span><span class="sxs-lookup"><span data-stu-id="38e8f-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="38e8f-103">此示例演示如何打开一个对话框。</span><span class="sxs-lookup"><span data-stu-id="38e8f-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38e8f-104">示例</span><span class="sxs-lookup"><span data-stu-id="38e8f-104">Example</span></span>  
 <span data-ttu-id="38e8f-105">对话框中是一种方法是实例化打开窗口<xref:System.Windows.Window>并调用<xref:System.Windows.Window.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="38e8f-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="38e8f-106"><xref:System.Windows.Window.ShowDialog%2A>将打开一个窗口，并且不返回之前已关闭新建对话框。</span><span class="sxs-lookup"><span data-stu-id="38e8f-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="38e8f-107">这种类型的窗口是也称为*模式*窗口中，它会限制用户输入。</span><span class="sxs-lookup"><span data-stu-id="38e8f-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="38e8f-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="38e8f-108">.NET Framework Security</span></span>  
 <span data-ttu-id="38e8f-109">调用<xref:System.Windows.Window.ShowDialog%2A>需要有权使用所有窗口和不受限制的用户输入的事件。</span><span class="sxs-lookup"><span data-stu-id="38e8f-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e8f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38e8f-110">See Also</span></span>  
 [<span data-ttu-id="38e8f-111">返回对话框结果</span><span class="sxs-lookup"><span data-stu-id="38e8f-111">Return a Dialog Box Result</span></span>](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
