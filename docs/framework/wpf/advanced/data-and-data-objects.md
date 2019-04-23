---
title: 数据和数据对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: 9dc195ece60739cf0c137a2893c9e9150e0d4d3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312054"
---
# <a name="data-and-data-objects"></a><span data-ttu-id="13924-102">数据和数据对象</span><span class="sxs-lookup"><span data-stu-id="13924-102">Data and Data Objects</span></span>
<span data-ttu-id="13924-103">拖放操作的一部分传输的数据存储在数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-103">Data that is transferred as part of a drag-and-drop operation is stored in a data object.</span></span>  <span data-ttu-id="13924-104">从概念上讲，数据对象包含一个或多个以下对：</span><span class="sxs-lookup"><span data-stu-id="13924-104">Conceptually, a data object consists of one or more of the following pairs:</span></span>  
  
-   <span data-ttu-id="13924-105"><xref:System.Object> ，其中包含实际数据。</span><span class="sxs-lookup"><span data-stu-id="13924-105">An <xref:System.Object> that contains the actual data.</span></span>  
  
-   <span data-ttu-id="13924-106">对应的数据格式标识符。</span><span class="sxs-lookup"><span data-stu-id="13924-106">A corresponding data format identifier.</span></span>  
  
 <span data-ttu-id="13924-107">数据本身可以包含任何可以表示为基本<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="13924-107">The data itself can consist of anything that can be represented as a base <xref:System.Object>.</span></span>  <span data-ttu-id="13924-108">相应的数据格式是一个字符串或<xref:System.Type>，它提供有关设置数据的格式的提示是在中。</span><span class="sxs-lookup"><span data-stu-id="13924-108">The corresponding data format is a string or <xref:System.Type> that provides a hint about what format the data is in.</span></span>  <span data-ttu-id="13924-109">数据对象支持托管多个数据/数据格式对;这样一个数据对象提供多种格式的数据。</span><span class="sxs-lookup"><span data-stu-id="13924-109">Data objects support hosting multiple data/data format pairs; this enables a single data object to provide data in multiple formats.</span></span>  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a><span data-ttu-id="13924-110">数据对象</span><span class="sxs-lookup"><span data-stu-id="13924-110">Data Objects</span></span>  
 <span data-ttu-id="13924-111">所有数据对象必须都实现<xref:System.Windows.IDataObject>接口，它提供了启用和进行数据传输方法的以下标准集。</span><span class="sxs-lookup"><span data-stu-id="13924-111">All data objects must implement the <xref:System.Windows.IDataObject> interface, which provides the following standard set of methods that enable and facilitate data transfer.</span></span>  
  
|<span data-ttu-id="13924-112">方法</span><span class="sxs-lookup"><span data-stu-id="13924-112">Method</span></span>|<span data-ttu-id="13924-113">总结</span><span class="sxs-lookup"><span data-stu-id="13924-113">Summary</span></span>|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|<span data-ttu-id="13924-114">检索指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-114">Retrieves a data object in a specified data format.</span></span>|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|<span data-ttu-id="13924-115">检查以查看是否现已推出，或者可以转换为指定格式数据。</span><span class="sxs-lookup"><span data-stu-id="13924-115">Checks to see whether the data is available in, or can be converted to, a specified format.</span></span>|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|<span data-ttu-id="13924-116">返回此数据对象中的数据存储，或可以转换为的格式的列表。</span><span class="sxs-lookup"><span data-stu-id="13924-116">Returns a list of formats that the data in this data object is stored in, or can be converted to.</span></span>|  
|<xref:System.Windows.IDataObject.SetData%2A>|<span data-ttu-id="13924-117">此数据对象中存储指定的数据。</span><span class="sxs-lookup"><span data-stu-id="13924-117">Stores the specified data in this data object.</span></span>|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="13924-118">提供的基本实现<xref:System.Windows.IDataObject>在<xref:System.Windows.DataObject>类。</span><span class="sxs-lookup"><span data-stu-id="13924-118">provides a basic implementation of <xref:System.Windows.IDataObject> in the <xref:System.Windows.DataObject> class.</span></span> <span data-ttu-id="13924-119">股票<xref:System.Windows.DataObject>类足以满足许多常见的数据传输方案。</span><span class="sxs-lookup"><span data-stu-id="13924-119">The stock <xref:System.Windows.DataObject> class is sufficient for many common data transfer scenarios.</span></span>  
  
 <span data-ttu-id="13924-120">有几个预定义的格式，如位图、 CSV、 文件、 HTML、 RTF、 字符串、 文本和音频。</span><span class="sxs-lookup"><span data-stu-id="13924-120">There are several pre-defined formats, such as bitmap, CSV, file, HTML, RTF, string, text, and audio.</span></span> <span data-ttu-id="13924-121">有关随一起提供的预定义的数据格式信息[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅<xref:System.Windows.DataFormats>类参考主题。</span><span class="sxs-lookup"><span data-stu-id="13924-121">For information about pre-defined data formats provided with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see the <xref:System.Windows.DataFormats> class reference topic.</span></span>  
  
 <span data-ttu-id="13924-122">数据对象通常包括一个工具，以便自动将转换为其他格式的一种格式中提取数据; 时存储的数据此工具称为自动转换。</span><span class="sxs-lookup"><span data-stu-id="13924-122">Data objects commonly include a facility for automatically converting data stored in one format to a different format while extracting data; this facility is referred to as auto-convert.</span></span> <span data-ttu-id="13924-123">查询时可用的数据对象中的数据格式，可以通过调用筛选从本机数据格式自动转换的数据格式<xref:System.Windows.DataObject.GetFormats%28System.Boolean%29>或<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>方法并指定`autoConvert`作为参数`false`。</span><span class="sxs-lookup"><span data-stu-id="13924-123">When querying for the data formats available in a data object, auto-convertible data formats can be filtered from native data formats by calling the <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> or <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> method and specifying the `autoConvert` parameter as `false`.</span></span>  <span data-ttu-id="13924-124">将数据添加到具有的数据对象时<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29>方法，自动转换的数据，可以通过设置禁止`autoConvert`参数`false`。</span><span class="sxs-lookup"><span data-stu-id="13924-124">When adding data to a data object with the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> method, auto-conversion of data can be prohibited by setting the `autoConvert` parameter to `false`.</span></span>  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a><span data-ttu-id="13924-125">使用数据对象</span><span class="sxs-lookup"><span data-stu-id="13924-125">Working with Data Objects</span></span>  
 <span data-ttu-id="13924-126">本部分介绍用于创建和使用数据对象的常见方法。</span><span class="sxs-lookup"><span data-stu-id="13924-126">This section describes common techniques for creating and working with data objects.</span></span>  
  
### <a name="creating-new-data-objects"></a><span data-ttu-id="13924-127">创建新的数据对象</span><span class="sxs-lookup"><span data-stu-id="13924-127">Creating New Data Objects</span></span>  
 <span data-ttu-id="13924-128"><xref:System.Windows.DataObject>类提供了多个重载的构造函数，便于您填充一个新<xref:System.Windows.DataObject>具有单一数据格式对实例。</span><span class="sxs-lookup"><span data-stu-id="13924-128">The <xref:System.Windows.DataObject> class provides several overloaded constructors that facilitate populating a new <xref:System.Windows.DataObject> instance with a single data/data format pair.</span></span>  
  
 <span data-ttu-id="13924-129">下面的代码示例创建一个新的数据对象，并使用重载的构造函数之一<xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-129">The following example code creates a new data object and uses one of the overloaded constructors <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="13924-130">一个字符串; 在这种情况下，指定数据格式<xref:System.Windows.DataFormats>类提供了一组预定义的类型字符串。</span><span class="sxs-lookup"><span data-stu-id="13924-130">In this case, the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="13924-131">默认情况下允许存储的数据的自动转换。</span><span class="sxs-lookup"><span data-stu-id="13924-131">Auto-conversion of the stored data is allowed by default.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 <span data-ttu-id="13924-132">有关创建数据对象的代码的更多示例，请参阅[创建数据对象](how-to-create-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="13924-132">For more examples of code that creates a data object, see [Create a Data Object](how-to-create-a-data-object.md).</span></span>  
  
### <a name="storing-data-in-multiple-formats"></a><span data-ttu-id="13924-133">以多种格式存储数据</span><span class="sxs-lookup"><span data-stu-id="13924-133">Storing Data in Multiple Formats</span></span>  
 <span data-ttu-id="13924-134">单个数据对象是能够以多种格式存储数据。</span><span class="sxs-lookup"><span data-stu-id="13924-134">A single data object is able to store data in multiple formats.</span></span>   <span data-ttu-id="13924-135">战略使用单个数据对象中的多种数据格式可能会使数据对象可以使用更多种类的放置目标比如果仅可以表示单一数据格式。</span><span class="sxs-lookup"><span data-stu-id="13924-135">Strategic use of multiple data formats within a single data object potentially makes the data object consumable by a wider variety of drop targets than if only a single data format could be represented.</span></span>  <span data-ttu-id="13924-136">请注意，一般情况下，拖动源必须是不可知的数据格式的使用可能放置目标的索引。</span><span class="sxs-lookup"><span data-stu-id="13924-136">Note that, in general, a drag source must be agnostic about the data formats that are consumable by potential drop targets.</span></span>  
  
 <span data-ttu-id="13924-137">下面的示例演示如何使用<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>方法将数据添加到多个格式中的数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-137">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a><span data-ttu-id="13924-138">查询可用的格式数据对象</span><span class="sxs-lookup"><span data-stu-id="13924-138">Querying a Data Object for Available Formats</span></span>  
 <span data-ttu-id="13924-139">由于单个数据对象可以包含任意数目的数据格式，数据对象包含用于检索可用的数据格式的列表的功能。</span><span class="sxs-lookup"><span data-stu-id="13924-139">Because a single data object can contain an arbitrary number of data formats, data objects include facilities for retrieving a list of available data formats.</span></span>  
  
 <span data-ttu-id="13924-140">下面的示例代码使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示所有可用数据对象 （本机和通过自动转换） 中的数据格式的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="13924-140">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and by auto-convert).</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 <span data-ttu-id="13924-141">查询可用的数据格式的数据对象的代码的更多示例，请参阅[列出数据对象中的数据格式](how-to-list-the-data-formats-in-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="13924-141">For more examples of code that queries a data object for available data formats, see [List the Data Formats in a Data Object](how-to-list-the-data-formats-in-a-data-object.md).</span></span>  <span data-ttu-id="13924-142">查询是否存在特定的数据格式的数据对象的示例，请参阅[确定数据格式是否存在于数据对象中](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="13924-142">For examples of querying a data object for the presence of a particular data format, see [Determine if a Data Format is Present in a Data Object](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).</span></span>  
  
### <a name="retrieving-data-from-a-data-object"></a><span data-ttu-id="13924-143">从数据对象中检索数据</span><span class="sxs-lookup"><span data-stu-id="13924-143">Retrieving Data from a Data Object</span></span>  
 <span data-ttu-id="13924-144">从特定格式的数据对象中检索数据仅涉及调用之一<xref:System.Windows.DataObject.GetData%2A>方法并指定所需的数据格式。</span><span class="sxs-lookup"><span data-stu-id="13924-144">Retrieving data from a data object in a particular format simply involves calling one of the <xref:System.Windows.DataObject.GetData%2A> methods and specifying the desired data format.</span></span>  <span data-ttu-id="13924-145">其中一个<xref:System.Windows.DataObject.GetDataPresent%2A>方法可用于检查是否存在特定的数据格式。</span><span class="sxs-lookup"><span data-stu-id="13924-145">One of the <xref:System.Windows.DataObject.GetDataPresent%2A> methods can be used to check for the presence of a particular data format.</span></span>  <span data-ttu-id="13924-146"><xref:System.Windows.DataObject.GetData%2A> 在将数据返回<xref:System.Object>; 具体取决于数据格式，此对象可强制转换为特定于类型的容器。</span><span class="sxs-lookup"><span data-stu-id="13924-146"><xref:System.Windows.DataObject.GetData%2A> returns the data in an <xref:System.Object>; depending on the data format, this object can be cast to a type-specific container.</span></span>  
  
 <span data-ttu-id="13924-147">下面的示例代码使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>重载来检查是否可指定的数据格式 （本机编译或通过自动转换）。</span><span class="sxs-lookup"><span data-stu-id="13924-147">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to check if a specified data format is available (native or by auto-convert).</span></span> <span data-ttu-id="13924-148">如果指定的格式不可用，该示例通过检索数据<xref:System.Windows.DataObject.GetData%28System.String%29>方法。</span><span class="sxs-lookup"><span data-stu-id="13924-148">If the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 <span data-ttu-id="13924-149">数据对象中检索数据的代码的更多示例，请参阅[特定数据格式检索数据](how-to-retrieve-data-in-a-particular-data-format.md)。</span><span class="sxs-lookup"><span data-stu-id="13924-149">For more examples of code that retrieves data from a data object, see [Retrieve Data in a Particular Data Format](how-to-retrieve-data-in-a-particular-data-format.md).</span></span>  
  
### <a name="removing-data-from-a-data-object"></a><span data-ttu-id="13924-150">从数据对象中删除数据</span><span class="sxs-lookup"><span data-stu-id="13924-150">Removing Data From a Data Object</span></span>  
 <span data-ttu-id="13924-151">从数据对象不能直接删除数据。</span><span class="sxs-lookup"><span data-stu-id="13924-151">Data cannot be directly removed from a data object.</span></span>  <span data-ttu-id="13924-152">若要有效地从数据对象中删除数据，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="13924-152">To effectively remove data from a data object, follow these steps:</span></span>  
  
1. <span data-ttu-id="13924-153">创建新的数据对象将包含你想要保留数据。</span><span class="sxs-lookup"><span data-stu-id="13924-153">Create a new data object that will contain only the data you want to retain.</span></span>  
  
2. <span data-ttu-id="13924-154">"复制"到新的数据对象从旧的数据对象所需的数据。</span><span class="sxs-lookup"><span data-stu-id="13924-154">"Copy" the desired data from the old data object to the new data object.</span></span>  <span data-ttu-id="13924-155">若要复制数据，请使用之一<xref:System.Windows.DataObject.GetData%2A>方法来检索<xref:System.Object>，其中包含原始数据，然后执行下列任一<xref:System.Windows.DataObject.SetData%2A>方法将数据添加到新的数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-155">To copy the data, use one of the <xref:System.Windows.DataObject.GetData%2A> methods to retrieve an <xref:System.Object> that contains the raw data, and then use one of the <xref:System.Windows.DataObject.SetData%2A> methods to add the data to the new data object.</span></span>  
  
3. <span data-ttu-id="13924-156">替换为新旧数据对象。</span><span class="sxs-lookup"><span data-stu-id="13924-156">Replace the old data object with the new one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13924-157"><xref:System.Windows.DataObject.SetData%2A>方法仅将数据添加到数据对象; 但仍数据，即使数据和数据格式完全与上一次调用相同。</span><span class="sxs-lookup"><span data-stu-id="13924-157">The <xref:System.Windows.DataObject.SetData%2A> methods only add data to a data object; they do not replace data, even if the data and data format are exactly the same as a previous call.</span></span> <span data-ttu-id="13924-158">调用<xref:System.Windows.DataObject.SetData%2A>两次以相同的数据和数据格式将导致数据/数据格式存在的数据对象中两次。</span><span class="sxs-lookup"><span data-stu-id="13924-158">Calling <xref:System.Windows.DataObject.SetData%2A> twice for the same data and data format will result in the data/data format being present twice in the data object.</span></span>
