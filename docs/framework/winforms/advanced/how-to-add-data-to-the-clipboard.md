---
title: "如何：将数据添加到剪贴板"
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
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="0f298-102">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="0f298-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="0f298-103"><xref:System.Windows.Forms.Clipboard>类提供了可以使用与 Windows 操作系统的剪贴板功能进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="0f298-104">许多应用程序的数据作为临时存储库使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0f298-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="0f298-105">例如，字处理器在剪切和粘贴操作期间使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0f298-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="0f298-106">剪贴板还可用于将数据传输到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f298-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="0f298-107">当将数据添加到剪贴板时，你可以指示的数据格式，以便其他应用程序能够识别数据，如果它们可以使用该格式。</span><span class="sxs-lookup"><span data-stu-id="0f298-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="0f298-108">到剪贴板中多个不同的格式，增加其他应用程序可能会使用数据的数量，你还可以添加数据。</span><span class="sxs-lookup"><span data-stu-id="0f298-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="0f298-109">剪贴板格式是一个字符串，标识格式，以便使用该格式的应用程序可以检索关联的数据。</span><span class="sxs-lookup"><span data-stu-id="0f298-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="0f298-110"><xref:System.Windows.Forms.DataFormats>类提供了供你使用的预定义的格式名。</span><span class="sxs-lookup"><span data-stu-id="0f298-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="0f298-111">你可以使用你自己的格式名，或用作其格式的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="0f298-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="0f298-112">若要将数据添加到剪贴板中一个或多个格式，使用<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="0f298-113">可以将任何对象传递给此方法，但若要添加多个格式数据，你必须首先将数据添加到一个单独的对象设计为可以使用多种格式。</span><span class="sxs-lookup"><span data-stu-id="0f298-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="0f298-114">通常情况下，你将添加到你的数据<xref:System.Windows.Forms.DataObject>，但你可以使用实现任何类型<xref:System.Windows.Forms.IDataObject>接口。</span><span class="sxs-lookup"><span data-stu-id="0f298-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="0f298-115">在[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]，你可以直接向剪贴板添加数据，通过使用为简化了基本剪贴板任务而设计的新方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="0f298-116">当您使用单一的常用格式，例如文本中的数据时，请使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f298-117">所有基于 Windows 的应用程序共享剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0f298-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="0f298-118">因此，内容可能会发生更改时切换到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f298-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="0f298-119"><xref:System.Windows.Forms.Clipboard>类仅在设置为单线程单元 (STA) 模式的线程中使用。</span><span class="sxs-lookup"><span data-stu-id="0f298-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="0f298-120">若要使用此类，请确保你`Main`方法标记为<xref:System.STAThreadAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="0f298-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="0f298-121">对象必须可序列化，才能将其放在剪贴板上。</span><span class="sxs-lookup"><span data-stu-id="0f298-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="0f298-122">若要使类型可序列化，将其与标记<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="0f298-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="0f298-123">如果将非可序列化对象传递给剪贴板方法时，该方法将失败而不引发异常。</span><span class="sxs-lookup"><span data-stu-id="0f298-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="0f298-124">有关序列化的详细信息，请参阅<xref:System.Runtime.Serialization>。</span><span class="sxs-lookup"><span data-stu-id="0f298-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="0f298-125">若要将数据添加到剪贴板中单一的常用格式</span><span class="sxs-lookup"><span data-stu-id="0f298-125">To add data to the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="0f298-126">使用<xref:System.Windows.Forms.Clipboard.SetAudio%2A>， <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>， <xref:System.Windows.Forms.Clipboard.SetImage%2A>，或<xref:System.Windows.Forms.Clipboard.SetText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="0f298-127">这些方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f298-127">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="0f298-128">若要将数据添加到剪贴板中自定义格式</span><span class="sxs-lookup"><span data-stu-id="0f298-128">To add data to the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="0f298-129">使用<xref:System.Windows.Forms.Clipboard.SetData%2A>具有自定义格式名称方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="0f298-130">此方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f298-130">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="0f298-131">你还可以使用与预定义的格式名<xref:System.Windows.Forms.Clipboard.SetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0f298-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="0f298-132">有关详细信息，请参阅<xref:System.Windows.Forms.DataFormats>。</span><span class="sxs-lookup"><span data-stu-id="0f298-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="0f298-133">若要将数据添加到剪贴板中多种格式</span><span class="sxs-lookup"><span data-stu-id="0f298-133">To add data to the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="0f298-134">使用<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>方法并传入<xref:System.Windows.Forms.DataObject>，其中包含你的数据。</span><span class="sxs-lookup"><span data-stu-id="0f298-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="0f298-135">你必须使用此方法将数据添加到剪贴板上版本早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f298-135">You must use this method to add data to the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="0f298-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f298-136">See Also</span></span>  
 [<span data-ttu-id="0f298-137">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="0f298-137">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="0f298-138">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="0f298-138">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
