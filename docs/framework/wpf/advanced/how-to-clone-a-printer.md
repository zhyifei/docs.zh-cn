---
title: 如何：克隆打印机
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: 09a445da068f0141b9526e0228df8be0105498c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776540"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="8c5a5-102">如何：克隆打印机</span><span class="sxs-lookup"><span data-stu-id="8c5a5-102">How to: Clone a Printer</span></span>
<span data-ttu-id="8c5a5-103">大多数企业都在某些时候，将购买的同一模型的多台打印机。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="8c5a5-104">通常情况下，这些进行所有安装使用几乎完全相同的配置设置。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="8c5a5-105">安装每个打印机可能非常耗时且容易出错。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="8c5a5-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType>命名空间和<xref:System.Printing.PrintServer.InstallPrintQueue%2A>都通过 Microsoft.NET Framework 公开的类可以立即从现有的打印队列安装任意数目的克隆的其他打印队列。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5a5-107">示例</span><span class="sxs-lookup"><span data-stu-id="8c5a5-107">Example</span></span>  
 <span data-ttu-id="8c5a5-108">在下面的示例中，第二个打印队列进行克隆现有的打印队列。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="8c5a5-109">第二个与前者区别仅在其名称、 位置、 端口和共享的状态中。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="8c5a5-110">执行此操作的主要步骤如下所示。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="8c5a5-111">创建<xref:System.Printing.PrintQueue>现有打印机要克隆的对象。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="8c5a5-112">创建<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>从<xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>的<xref:System.Printing.PrintQueue>。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="8c5a5-113"><xref:System.Collections.DictionaryEntry.Value%2A>此字典中的每个条目的属性是一个派生自的类型的一个对象<xref:System.Printing.IndexedProperties.PrintProperty>。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="8c5a5-114">有两种方法来设置此字典中的条目的值。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="8c5a5-115">使用字典**删除**和<xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A>方法来删除该项，然后重新将其添加具有所需的值。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="8c5a5-116">使用字典的<xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="8c5a5-117">下面的示例说明了这两种方式。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="8c5a5-118">创建<xref:System.Printing.IndexedProperties.PrintBooleanProperty>对象，并将其<xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>到"IsShared"并将其<xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A>到`true`。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="8c5a5-119">使用<xref:System.Printing.IndexedProperties.PrintBooleanProperty>对象的值<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>的"IsShared"条目。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="8c5a5-120">创建<xref:System.Printing.IndexedProperties.PrintStringProperty>对象，并将其<xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>到"共享名"并将其<xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>对相应<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="8c5a5-121">使用<xref:System.Printing.IndexedProperties.PrintStringProperty>对象的值<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>的"共享名"条目。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="8c5a5-122">创建另一个<xref:System.Printing.IndexedProperties.PrintStringProperty>对象，并将其<xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>到"位置"并将其<xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>对相应<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="8c5a5-123">使用第二个<xref:System.Printing.IndexedProperties.PrintStringProperty>对象的值<xref:System.Printing.IndexedProperties.PrintPropertyDictionary>的"位置"条目。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="8c5a5-124">创建一个数组<xref:System.String>s。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="8c5a5-125">每个项是端口的在服务器上的名称。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="8c5a5-126">使用<xref:System.Printing.PrintServer.InstallPrintQueue%2A>以使用新值进行安装新的打印机。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="8c5a5-127">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="8c5a5-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="8c5a5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c5a5-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="8c5a5-129">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="8c5a5-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="8c5a5-130">打印概述</span><span class="sxs-lookup"><span data-stu-id="8c5a5-130">Printing Overview</span></span>](printing-overview.md)
