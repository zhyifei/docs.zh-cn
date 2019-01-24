---
title: 如何：验证和合并 PrintTicket
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 0b9f7b101ea4f06c86f66f8e4e16d1ffeabaa9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671936"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="8e965-102">如何：验证和合并 PrintTicket</span><span class="sxs-lookup"><span data-stu-id="8e965-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="8e965-103">[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [打印架构](https://go.microsoft.com/fwlink/?LinkId=186397)包括灵活且可扩展<xref:System.Printing.PrintCapabilities>和<xref:System.Printing.PrintTicket>元素。</span><span class="sxs-lookup"><span data-stu-id="8e965-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="8e965-104">前者详细列举的打印设备的功能，后者用于指定设备应如何使用这些功能来处理特定文档、 单个文档或单页的序列。</span><span class="sxs-lookup"><span data-stu-id="8e965-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="8e965-105">典型的应用程序支持打印的任务序列将如下所示。</span><span class="sxs-lookup"><span data-stu-id="8e965-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="8e965-106">确定打印机的功能。</span><span class="sxs-lookup"><span data-stu-id="8e965-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="8e965-107">配置<xref:System.Printing.PrintTicket>以使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="8e965-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="8e965-108">验证<xref:System.Printing.PrintTicket>。</span><span class="sxs-lookup"><span data-stu-id="8e965-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="8e965-109">本文介绍如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8e965-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e965-110">示例</span><span class="sxs-lookup"><span data-stu-id="8e965-110">Example</span></span>  
 <span data-ttu-id="8e965-111">在下面的简单示例中，我们都只希望打印机是否支持双工 — 双面打印。</span><span class="sxs-lookup"><span data-stu-id="8e965-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="8e965-112">主要步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="8e965-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="8e965-113">获取<xref:System.Printing.PrintCapabilities>对象与<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8e965-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="8e965-114">测试存在所需的功能。</span><span class="sxs-lookup"><span data-stu-id="8e965-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="8e965-115">在以下示例中，我们测试<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>属性的<xref:System.Printing.PrintCapabilities>沿长边工作表的对象的一张纸的纸张的"翻页"的两面上的打印功能是否存在。</span><span class="sxs-lookup"><span data-stu-id="8e965-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="8e965-116">由于<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>是一个集合，我们将使用`Contains`方法的<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="8e965-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e965-117">此步骤不是绝对必需的。</span><span class="sxs-lookup"><span data-stu-id="8e965-117">This step is not strictly necessary.</span></span> <span data-ttu-id="8e965-118"><xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>使用以下方法将检查每个请求<xref:System.Printing.PrintTicket>针对打印机的功能。</span><span class="sxs-lookup"><span data-stu-id="8e965-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="8e965-119">如果打印机不支持请求的功能，打印机驱动程序将替换中的另一个请求<xref:System.Printing.PrintTicket>方法返回。</span><span class="sxs-lookup"><span data-stu-id="8e965-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="8e965-120">如果打印机支持双面打印，示例代码会创建<xref:System.Printing.PrintTicket>的要求进行双面打印。</span><span class="sxs-lookup"><span data-stu-id="8e965-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="8e965-121">但应用程序未指定每个可能的打印机设置中提供<xref:System.Printing.PrintTicket>元素。</span><span class="sxs-lookup"><span data-stu-id="8e965-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="8e965-122">这将浪费的程序员和计划时间。</span><span class="sxs-lookup"><span data-stu-id="8e965-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="8e965-123">相反，该代码设置仅进行双面打印请求，然后将合并这<xref:System.Printing.PrintTicket>与某个现有，完全配置且经过验证， <xref:System.Printing.PrintTicket>，在这种情况下，用户的默认<xref:System.Printing.PrintTicket>。</span><span class="sxs-lookup"><span data-stu-id="8e965-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="8e965-124">相应地，示例代码会调用<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>方法来合并将新的、 最小，<xref:System.Printing.PrintTicket>用户的默认值<xref:System.Printing.PrintTicket>。</span><span class="sxs-lookup"><span data-stu-id="8e965-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="8e965-125">这将返回<xref:System.Printing.ValidationResult>，包含新的<xref:System.Printing.PrintTicket>作为其属性之一。</span><span class="sxs-lookup"><span data-stu-id="8e965-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="8e965-126">此示例然后测试新<xref:System.Printing.PrintTicket>请求双面打印。</span><span class="sxs-lookup"><span data-stu-id="8e965-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="8e965-127">如果是这样，则代码会将其用户的新的默认打印票证。</span><span class="sxs-lookup"><span data-stu-id="8e965-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="8e965-128">如果没有执行上述步骤 2，并且打印机不支持双工沿长边，则测试将会造成`false`。</span><span class="sxs-lookup"><span data-stu-id="8e965-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="8e965-129">（请参阅上面的说明。）</span><span class="sxs-lookup"><span data-stu-id="8e965-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="8e965-130">最后一个重要步骤是将提交到更改<xref:System.Printing.PrintQueue.UserPrintTicket%2A>的属性<xref:System.Printing.PrintQueue>与<xref:System.Printing.PrintQueue.Commit%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8e965-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="8e965-131">以便可以快速测试此示例中，如下所示的其余部分。</span><span class="sxs-lookup"><span data-stu-id="8e965-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="8e965-132">创建项目和命名空间，然后将在本文中的两个代码片段粘贴到命名空间块。</span><span class="sxs-lookup"><span data-stu-id="8e965-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="8e965-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e965-133">See also</span></span>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="8e965-134">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="8e965-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="8e965-135">打印概述</span><span class="sxs-lookup"><span data-stu-id="8e965-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [<span data-ttu-id="8e965-136">打印架构</span><span class="sxs-lookup"><span data-stu-id="8e965-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
