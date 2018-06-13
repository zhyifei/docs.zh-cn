---
title: 如何： 返回对话框结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 8f754577a355a58060238bbbb487c36aea14658c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545582"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="6405d-102">如何： 返回对话框结果</span><span class="sxs-lookup"><span data-stu-id="6405d-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="6405d-103">此示例演示如何检索一个窗口，通过调用打开的对话框结果<xref:System.Windows.Window.ShowDialog%2A>。</span><span class="sxs-lookup"><span data-stu-id="6405d-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6405d-104">示例</span><span class="sxs-lookup"><span data-stu-id="6405d-104">Example</span></span>  
 <span data-ttu-id="6405d-105">在对话框关闭之前，其<xref:System.Windows.Window.DialogResult%2A>属性应设置与<xref:System.Nullable%601> <xref:System.Boolean> ，该值指示用户如何关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="6405d-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="6405d-106">此值由返回<xref:System.Windows.Window.ShowDialog%2A>以允许客户端代码，以确定如何关闭对话框中，因此，如何处理的结果。</span><span class="sxs-lookup"><span data-stu-id="6405d-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6405d-107"><xref:System.Windows.Window.DialogResult%2A> 当通过调用来打开窗口时才可以设置<xref:System.Windows.Window.ShowDialog%2A>。</span><span class="sxs-lookup"><span data-stu-id="6405d-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="6405d-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="6405d-108">.NET Framework Security</span></span>  
 <span data-ttu-id="6405d-109">调用<xref:System.Windows.Window.ShowDialog%2A>需要有权使用所有窗口和不受限制的用户输入的事件。</span><span class="sxs-lookup"><span data-stu-id="6405d-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
