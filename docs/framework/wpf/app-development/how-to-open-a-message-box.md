---
title: "如何： 打开一个消息框"
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
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 302a3cd34d90d47e38af1bbeaadca7e777a26395
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="7f380-102">如何： 打开一个消息框</span><span class="sxs-lookup"><span data-stu-id="7f380-102">How to: Open a Message Box</span></span>
<span data-ttu-id="7f380-103">此示例演示如何以打开一个消息框。</span><span class="sxs-lookup"><span data-stu-id="7f380-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f380-104">示例</span><span class="sxs-lookup"><span data-stu-id="7f380-104">Example</span></span>  
 <span data-ttu-id="7f380-105">消息框是一种预制模式对话框用于向用户显示信息。</span><span class="sxs-lookup"><span data-stu-id="7f380-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="7f380-106">通过调用静态打开一个消息框<xref:System.Windows.MessageBox.Show%2A>方法<xref:System.Windows.MessageBox>类。</span><span class="sxs-lookup"><span data-stu-id="7f380-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="7f380-107">当<xref:System.Windows.MessageBox.Show%2A>是调用，则消息将传递使用字符串参数。</span><span class="sxs-lookup"><span data-stu-id="7f380-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="7f380-108">几个重载<xref:System.Windows.MessageBox.Show%2A>允许你配置如何将出现一个消息框 (请参阅<xref:System.Windows.MessageBox>)。</span><span class="sxs-lookup"><span data-stu-id="7f380-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="7f380-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f380-109">See Also</span></span>  
 [<span data-ttu-id="7f380-110">消息框示例</span><span class="sxs-lookup"><span data-stu-id="7f380-110">MessageBox Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160023)
