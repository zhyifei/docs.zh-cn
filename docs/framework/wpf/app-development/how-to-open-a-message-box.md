---
title: 如何： 打开一个消息框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: f05190030ed6324917348fa1926abd5385e30f7e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47173390"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="5c4a8-102">如何： 打开一个消息框</span><span class="sxs-lookup"><span data-stu-id="5c4a8-102">How to: Open a Message Box</span></span>
<span data-ttu-id="5c4a8-103">此示例演示如何以打开一个消息框。</span><span class="sxs-lookup"><span data-stu-id="5c4a8-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c4a8-104">示例</span><span class="sxs-lookup"><span data-stu-id="5c4a8-104">Example</span></span>  
 <span data-ttu-id="5c4a8-105">消息框是一种预制模式对话框用于向用户显示的信息。</span><span class="sxs-lookup"><span data-stu-id="5c4a8-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="5c4a8-106">一个消息框打开通过调用静态<xref:System.Windows.MessageBox.Show%2A>方法的<xref:System.Windows.MessageBox>类。</span><span class="sxs-lookup"><span data-stu-id="5c4a8-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="5c4a8-107">当<xref:System.Windows.MessageBox.Show%2A>是调用，该消息使用传递的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="5c4a8-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="5c4a8-108">几个重载<xref:System.Windows.MessageBox.Show%2A>允许你配置如何将出现一个消息框 (请参阅<xref:System.Windows.MessageBox>)。</span><span class="sxs-lookup"><span data-stu-id="5c4a8-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="5c4a8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c4a8-109">See Also</span></span>  
 [<span data-ttu-id="5c4a8-110">消息框示例</span><span class="sxs-lookup"><span data-stu-id="5c4a8-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
