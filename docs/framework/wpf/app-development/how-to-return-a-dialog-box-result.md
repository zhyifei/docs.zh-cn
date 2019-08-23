---
title: 如何：返回对话框结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968236"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="563e5-102">如何：返回对话框结果</span><span class="sxs-lookup"><span data-stu-id="563e5-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="563e5-103">此示例演示如何检索通过调用<xref:System.Windows.Window.ShowDialog%2A>打开的窗口的对话框结果。</span><span class="sxs-lookup"><span data-stu-id="563e5-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="563e5-104">示例</span><span class="sxs-lookup"><span data-stu-id="563e5-104">Example</span></span>  
 <span data-ttu-id="563e5-105">在对话框关闭之前, 应将<xref:System.Windows.Window.DialogResult%2A>其属性设置<xref:System.Nullable%601> <xref:System.Boolean>为, 指示用户如何关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="563e5-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="563e5-106">此值由<xref:System.Windows.Window.ShowDialog%2A>返回, 以允许客户端代码确定对话框的关闭方式, 进而确定如何处理结果。</span><span class="sxs-lookup"><span data-stu-id="563e5-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="563e5-107"><xref:System.Windows.Window.DialogResult%2A>仅当通过调用<xref:System.Windows.Window.ShowDialog%2A>打开了窗口时才能设置。</span><span class="sxs-lookup"><span data-stu-id="563e5-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="563e5-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="563e5-108">.NET Framework Security</span></span>  
 <span data-ttu-id="563e5-109">调用<xref:System.Windows.Window.ShowDialog%2A>需要权限以在没有限制的情况下使用所有窗口和用户输入事件。</span><span class="sxs-lookup"><span data-stu-id="563e5-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
