---
title: "如何：从剪贴板检索数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c009efe743865896341da268bd14bf24158df46d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="b2591-102">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="b2591-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="b2591-103"><xref:System.Windows.Forms.Clipboard>类提供了可以使用与 Windows 操作系统的剪贴板功能进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="b2591-104">许多应用程序的数据作为临时存储库使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b2591-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="b2591-105">例如，字处理器在剪切和粘贴操作期间使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b2591-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="b2591-106">剪贴板还可用于将信息传输到另一个应用程序中。</span><span class="sxs-lookup"><span data-stu-id="b2591-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="b2591-107">某些应用程序将数据存储在剪贴板中多种格式，增加其他应用程序可能会使用数据的数量。</span><span class="sxs-lookup"><span data-stu-id="b2591-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="b2591-108">剪贴板格式是用于标识格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="b2591-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="b2591-109">使用标识的格式的应用程序可以检索在剪贴板上关联的数据。</span><span class="sxs-lookup"><span data-stu-id="b2591-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="b2591-110"><xref:System.Windows.Forms.DataFormats>类提供了供你使用的预定义的格式名。</span><span class="sxs-lookup"><span data-stu-id="b2591-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="b2591-111">你可以使用你自己的格式名，或用作其格式的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="b2591-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="b2591-112">有关将数据添加到剪贴板的信息，请参阅[如何： 将数据添加到剪贴板](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b2591-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="b2591-113">若要确定剪贴板是否包含特定的格式的数据，使用之一`Contains`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="b2591-114">若要从剪贴板检索数据，使用之一`Get`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="b2591-115">这些方法是在新[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b2591-115">These methods are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
 <span data-ttu-id="b2591-116">从通过使用版本剪贴板访问数据早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]，使用<xref:System.Windows.Forms.Clipboard.GetDataObject%2A>方法调用的方法的返回和<xref:System.Windows.Forms.IDataObject>。</span><span class="sxs-lookup"><span data-stu-id="b2591-116">To access data from the Clipboard by using versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="b2591-117">若要确定特定的格式是否位于返回的对象，例如，调用<xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2591-118">所有基于 Windows 的应用程序共享系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b2591-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="b2591-119">因此，内容可能会发生更改时切换到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2591-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="b2591-120"><xref:System.Windows.Forms.Clipboard>类仅在设置为单线程单元 (STA) 模式的线程中使用。</span><span class="sxs-lookup"><span data-stu-id="b2591-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="b2591-121">若要使用此类，请确保你`Main`方法标记为<xref:System.STAThreadAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="b2591-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="b2591-122">若要从单一的常用格式在剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="b2591-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="b2591-123">使用<xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>， <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>， <xref:System.Windows.Forms.Clipboard.GetImage%2A>，或<xref:System.Windows.Forms.Clipboard.GetText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="b2591-124">（可选） 使用相应`Contains`*格式*方法，首先以确定数据是否可用的特定的格式。</span><span class="sxs-lookup"><span data-stu-id="b2591-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="b2591-125">这些方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b2591-125">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="b2591-126">若要从自定义格式剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="b2591-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="b2591-127">使用<xref:System.Windows.Forms.Clipboard.GetData%2A>具有自定义格式名称方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="b2591-128">此方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b2591-128">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="b2591-129">你还可以使用与预定义的格式名<xref:System.Windows.Forms.Clipboard.SetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="b2591-130">有关详细信息，请参阅<xref:System.Windows.Forms.DataFormats>。</span><span class="sxs-lookup"><span data-stu-id="b2591-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="b2591-131">若要从以多种格式剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="b2591-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="b2591-132">使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b2591-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="b2591-133">必须使用此方法来检索数据从剪贴板上版本早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b2591-133">You must use this method to retrieve data from the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="b2591-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2591-134">See Also</span></span>  
 [<span data-ttu-id="b2591-135">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="b2591-135">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="b2591-136">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="b2591-136">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
