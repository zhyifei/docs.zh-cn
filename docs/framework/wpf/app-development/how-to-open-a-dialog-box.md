---
title: 如何：打开对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084961"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="b03a7-102">如何：打开对话框</span><span class="sxs-lookup"><span data-stu-id="b03a7-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="b03a7-103">此示例演示如何以打开一个对话框。</span><span class="sxs-lookup"><span data-stu-id="b03a7-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b03a7-104">示例</span><span class="sxs-lookup"><span data-stu-id="b03a7-104">Example</span></span>  
 <span data-ttu-id="b03a7-105">对话框是通过实例化打开的窗口<xref:System.Windows.Window>并调用<xref:System.Windows.Window.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b03a7-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="b03a7-106"><xref:System.Windows.Window.ShowDialog%2A> 将打开一个窗口和新建对话框已关闭之前不会返回。</span><span class="sxs-lookup"><span data-stu-id="b03a7-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="b03a7-107">此类型的窗口是也称为*模式*窗口中，它会限制用户输入。</span><span class="sxs-lookup"><span data-stu-id="b03a7-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="b03a7-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="b03a7-108">.NET Framework Security</span></span>  
 <span data-ttu-id="b03a7-109">调用<xref:System.Windows.Window.ShowDialog%2A>需要有权使用所有窗口和不受限制的用户输入的事件。</span><span class="sxs-lookup"><span data-stu-id="b03a7-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03a7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b03a7-110">See also</span></span>

- [<span data-ttu-id="b03a7-111">返回对话框结果</span><span class="sxs-lookup"><span data-stu-id="b03a7-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
