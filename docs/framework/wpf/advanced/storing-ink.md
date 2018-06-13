---
title: 存储墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: d3d33be5e8b5cf9dd7e32a52dfc258aa934c5c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546092"
---
# <a name="storing-ink"></a><span data-ttu-id="1a46c-102">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="1a46c-102">Storing Ink</span></span>
<span data-ttu-id="1a46c-103"><xref:System.Windows.Ink.StrokeCollection.Save%2A>方法用于存储墨迹作为墨迹序列化格式 (ISF) 提供支持。</span><span class="sxs-lookup"><span data-stu-id="1a46c-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="1a46c-104">构造函数<xref:System.Windows.Ink.StrokeCollection>类为读取墨迹数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="1a46c-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="1a46c-105">墨迹存储和检索</span><span class="sxs-lookup"><span data-stu-id="1a46c-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="1a46c-106">本部分讨论如何存储和检索在墨迹[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]平台。</span><span class="sxs-lookup"><span data-stu-id="1a46c-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="1a46c-107">下面的示例实现一个按钮的 click 事件处理程序，向用户呈现保存文件对话框中，然后将保存从墨迹<xref:System.Windows.Controls.InkCanvas>出到一个文件。</span><span class="sxs-lookup"><span data-stu-id="1a46c-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="1a46c-108">下面的示例实现一个按钮的 click 事件处理程序，向用户呈现文件打开的对话框中，从文件读入读取墨迹<xref:System.Windows.Controls.InkCanvas>元素。</span><span class="sxs-lookup"><span data-stu-id="1a46c-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="1a46c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a46c-109">See Also</span></span>  
 <xref:System.Windows.Controls.InkCanvas>  
 [<span data-ttu-id="1a46c-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="1a46c-110">Windows Presentation Foundation</span></span>](../../../../docs/framework/wpf/index.md)
