---
title: 如何：从剪贴板检索数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: 868afc36f08571d16285d0df52f6d1cad8c9c7a6
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348205"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="1c2a2-102">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="1c2a2-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="1c2a2-103"><xref:System.Windows.Forms.Clipboard>类提供了可用于与 Windows 操作系统剪贴板功能进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="1c2a2-104">许多应用程序的数据用作临时存储库使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="1c2a2-105">例如，文字处理器剪切和粘贴操作期间使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="1c2a2-106">剪贴板功能也很有用信息传输到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="1c2a2-107">某些应用程序以增加数据有可能使用其他应用程序的数量以多种格式剪贴板上存储数据。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="1c2a2-108">剪贴板格式是用于标识格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="1c2a2-109">使用标识的格式的应用程序可以检索剪贴板上的关联的数据。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="1c2a2-110"><xref:System.Windows.Forms.DataFormats>类提供了供你使用的预定义的格式名称。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="1c2a2-111">此外可以使用自己的格式名称，或使用对象的类型作为其格式。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="1c2a2-112">有关将数据添加到剪贴板的信息，请参阅[如何：将数据添加到剪贴板](how-to-add-data-to-the-clipboard.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="1c2a2-113">若要确定剪贴板中是否包含特定格式的数据，请使用之一`Contains`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="1c2a2-114">若要从剪贴板检索数据，请使用之一`Get`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="1c2a2-115">这些方法是.NET Framework 2.0 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-115">These methods are new in .NET Framework 2.0.</span></span>  
  
 <span data-ttu-id="1c2a2-116">若要使用的版本早于.NET Framework 2.0 从剪贴板访问数据，使用<xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType>方法调用的方法所返回的<xref:System.Windows.Forms.IDataObject>。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-116">To access data from the Clipboard by using versions earlier than .NET Framework 2.0, use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="1c2a2-117">若要确定特定的格式是否可在返回的对象，例如，调用<xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c2a2-118">所有基于 Windows 的应用程序共享系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="1c2a2-119">因此，可能会有所变动时切换到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="1c2a2-120"><xref:System.Windows.Forms.Clipboard>类仅可在线程设置为单线程单元 (STA) 模式。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="1c2a2-121">若要使用此类，请确保你`Main`方法将标有<xref:System.STAThreadAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="1c2a2-122">若要从单个的常见格式在剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="1c2a2-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1. <span data-ttu-id="1c2a2-123">使用<xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>， <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>， <xref:System.Windows.Forms.Clipboard.GetImage%2A>，或<xref:System.Windows.Forms.Clipboard.GetText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="1c2a2-124">（可选） 使用的相应`Contains`*格式*首先确定数据是否采用特定格式的方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="1c2a2-125">这些方法是仅在.NET Framework 2.0 中可用。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-125">These methods are available only in .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="1c2a2-126">若要从自定义格式在剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="1c2a2-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1. <span data-ttu-id="1c2a2-127">使用<xref:System.Windows.Forms.Clipboard.GetData%2A>具有自定义格式名称的方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="1c2a2-128">此方法是仅在.NET Framework 2.0 中可用。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-128">This method is available only in .NET Framework 2.0.</span></span>  
  
     <span data-ttu-id="1c2a2-129">此外可以使用具有预定义的格式名称<xref:System.Windows.Forms.Clipboard.SetData%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="1c2a2-130">有关详细信息，请参阅 <xref:System.Windows.Forms.DataFormats>。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="1c2a2-131">若要从多个格式在剪贴板中检索数据</span><span class="sxs-lookup"><span data-stu-id="1c2a2-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1. <span data-ttu-id="1c2a2-132">使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="1c2a2-133">必须使用此方法以从早于.NET Framework 2.0 版本在剪贴板中检索数据。</span><span class="sxs-lookup"><span data-stu-id="1c2a2-133">You must use this method to retrieve data from the Clipboard on versions earlier than .NET Framework 2.0.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="1c2a2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2a2-134">See also</span></span>

- [<span data-ttu-id="1c2a2-135">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="1c2a2-135">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="1c2a2-136">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="1c2a2-136">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
