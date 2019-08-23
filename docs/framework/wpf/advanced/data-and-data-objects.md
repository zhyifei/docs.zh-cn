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
ms.openlocfilehash: 4b948a64a14df7ea79b54b810f734056d57ef406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964865"
---
# <a name="data-and-data-objects"></a><span data-ttu-id="577ec-102">数据和数据对象</span><span class="sxs-lookup"><span data-stu-id="577ec-102">Data and Data Objects</span></span>
<span data-ttu-id="577ec-103">作为拖放操作的一部分传输的数据存储在数据对象中。</span><span class="sxs-lookup"><span data-stu-id="577ec-103">Data that is transferred as part of a drag-and-drop operation is stored in a data object.</span></span>  <span data-ttu-id="577ec-104">从概念上讲, 数据对象由以下一个或多个对组成:</span><span class="sxs-lookup"><span data-stu-id="577ec-104">Conceptually, a data object consists of one or more of the following pairs:</span></span>  
  
- <span data-ttu-id="577ec-105">一个<xref:System.Object>包含实际数据的。</span><span class="sxs-lookup"><span data-stu-id="577ec-105">An <xref:System.Object> that contains the actual data.</span></span>  
  
- <span data-ttu-id="577ec-106">对应的数据格式标识符。</span><span class="sxs-lookup"><span data-stu-id="577ec-106">A corresponding data format identifier.</span></span>  
  
 <span data-ttu-id="577ec-107">数据本身可以包含可表示为基础<xref:System.Object>的任何内容。</span><span class="sxs-lookup"><span data-stu-id="577ec-107">The data itself can consist of anything that can be represented as a base <xref:System.Object>.</span></span>  <span data-ttu-id="577ec-108">对应的数据格式是一个字符串或<xref:System.Type> , 它提供有关数据所在格式的提示。</span><span class="sxs-lookup"><span data-stu-id="577ec-108">The corresponding data format is a string or <xref:System.Type> that provides a hint about what format the data is in.</span></span>  <span data-ttu-id="577ec-109">数据对象支持承载多个数据/数据格式对;这使得单个数据对象可以提供多种格式的数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-109">Data objects support hosting multiple data/data format pairs; this enables a single data object to provide data in multiple formats.</span></span>  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a><span data-ttu-id="577ec-110">数据对象</span><span class="sxs-lookup"><span data-stu-id="577ec-110">Data Objects</span></span>  
 <span data-ttu-id="577ec-111">所有数据对象必须实现<xref:System.Windows.IDataObject>接口, 该接口提供了以下标准方法集, 可启用和简化数据传输。</span><span class="sxs-lookup"><span data-stu-id="577ec-111">All data objects must implement the <xref:System.Windows.IDataObject> interface, which provides the following standard set of methods that enable and facilitate data transfer.</span></span>  
  
|<span data-ttu-id="577ec-112">方法</span><span class="sxs-lookup"><span data-stu-id="577ec-112">Method</span></span>|<span data-ttu-id="577ec-113">总结</span><span class="sxs-lookup"><span data-stu-id="577ec-113">Summary</span></span>|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|<span data-ttu-id="577ec-114">检索指定数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-114">Retrieves a data object in a specified data format.</span></span>|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|<span data-ttu-id="577ec-115">检查以确定数据是否可用, 或者是否可以转换为指定的格式。</span><span class="sxs-lookup"><span data-stu-id="577ec-115">Checks to see whether the data is available in, or can be converted to, a specified format.</span></span>|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|<span data-ttu-id="577ec-116">返回一个格式列表, 此数据对象中的数据存储在这些格式中, 或可以转换为这些格式。</span><span class="sxs-lookup"><span data-stu-id="577ec-116">Returns a list of formats that the data in this data object is stored in, or can be converted to.</span></span>|  
|<xref:System.Windows.IDataObject.SetData%2A>|<span data-ttu-id="577ec-117">在此数据对象中存储指定的数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-117">Stores the specified data in this data object.</span></span>|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="577ec-118">提供<xref:System.Windows.IDataObject> 类<xref:System.Windows.DataObject>中的的基本实现。</span><span class="sxs-lookup"><span data-stu-id="577ec-118">provides a basic implementation of <xref:System.Windows.IDataObject> in the <xref:System.Windows.DataObject> class.</span></span> <span data-ttu-id="577ec-119">Stock <xref:System.Windows.DataObject>类足以满足许多常见数据传输方案的需求。</span><span class="sxs-lookup"><span data-stu-id="577ec-119">The stock <xref:System.Windows.DataObject> class is sufficient for many common data transfer scenarios.</span></span>  
  
 <span data-ttu-id="577ec-120">有几种预定义的格式, 如位图、CSV、文件、HTML、RTF、字符串、文本和音频。</span><span class="sxs-lookup"><span data-stu-id="577ec-120">There are several pre-defined formats, such as bitmap, CSV, file, HTML, RTF, string, text, and audio.</span></span> <span data-ttu-id="577ec-121">有关随一起[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的预定义数据格式的信息, <xref:System.Windows.DataFormats>请参见类参考主题。</span><span class="sxs-lookup"><span data-stu-id="577ec-121">For information about pre-defined data formats provided with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see the <xref:System.Windows.DataFormats> class reference topic.</span></span>  
  
 <span data-ttu-id="577ec-122">数据对象通常包含用于在提取数据时自动将一种格式的数据转换为其他格式的功能;此功能称为自动转换。</span><span class="sxs-lookup"><span data-stu-id="577ec-122">Data objects commonly include a facility for automatically converting data stored in one format to a different format while extracting data; this facility is referred to as auto-convert.</span></span> <span data-ttu-id="577ec-123">查询数据对象中可用的数据格式时, 可以通过<xref:System.Windows.DataObject.GetFormats%28System.Boolean%29>调用或<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>方法并将`autoConvert`参数指定为`false`, 从本机数据格式筛选自动转换的数据格式。</span><span class="sxs-lookup"><span data-stu-id="577ec-123">When querying for the data formats available in a data object, auto-convertible data formats can be filtered from native data formats by calling the <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> or <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> method and specifying the `autoConvert` parameter as `false`.</span></span>  <span data-ttu-id="577ec-124">使用<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29>方法向数据对象添加数据时, 可以通过`autoConvert`将参数设置为来`false`禁止自动转换数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-124">When adding data to a data object with the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> method, auto-conversion of data can be prohibited by setting the `autoConvert` parameter to `false`.</span></span>  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a><span data-ttu-id="577ec-125">使用数据对象</span><span class="sxs-lookup"><span data-stu-id="577ec-125">Working with Data Objects</span></span>  
 <span data-ttu-id="577ec-126">本部分介绍用于创建和使用数据对象的常用技术。</span><span class="sxs-lookup"><span data-stu-id="577ec-126">This section describes common techniques for creating and working with data objects.</span></span>  
  
### <a name="creating-new-data-objects"></a><span data-ttu-id="577ec-127">创建新数据对象</span><span class="sxs-lookup"><span data-stu-id="577ec-127">Creating New Data Objects</span></span>  
 <span data-ttu-id="577ec-128">类提供多个重载构造函数, 这些构造函数<xref:System.Windows.DataObject>有助于使用单个数据/数据格式对来填充新的实例。 <xref:System.Windows.DataObject></span><span class="sxs-lookup"><span data-stu-id="577ec-128">The <xref:System.Windows.DataObject> class provides several overloaded constructors that facilitate populating a new <xref:System.Windows.DataObject> instance with a single data/data format pair.</span></span>  
  
 <span data-ttu-id="577ec-129">下面的代码示例创建一个新的数据对象, 并使用一个重载的<xref:System.Windows.DataObject.%23ctor%2A>构造<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>函数 () 来初始化具有字符串和指定数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-129">The following example code creates a new data object and uses one of the overloaded constructors <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="577ec-130">在这种情况下, 数据格式由字符串指定;<xref:System.Windows.DataFormats>类提供一组预定义类型字符串。</span><span class="sxs-lookup"><span data-stu-id="577ec-130">In this case, the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="577ec-131">默认情况下允许自动转换存储的数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-131">Auto-conversion of the stored data is allowed by default.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 <span data-ttu-id="577ec-132">有关创建数据对象的代码的更多示例, 请参阅[创建数据对象](how-to-create-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="577ec-132">For more examples of code that creates a data object, see [Create a Data Object](how-to-create-a-data-object.md).</span></span>  
  
### <a name="storing-data-in-multiple-formats"></a><span data-ttu-id="577ec-133">以多种格式存储数据</span><span class="sxs-lookup"><span data-stu-id="577ec-133">Storing Data in Multiple Formats</span></span>  
 <span data-ttu-id="577ec-134">单个数据对象能够以多种格式存储数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-134">A single data object is able to store data in multiple formats.</span></span>   <span data-ttu-id="577ec-135">在单个数据对象内使用多个数据格式时, 可能会使数据对象被更多的拖放目标使用, 而不是仅能表示一种数据格式。</span><span class="sxs-lookup"><span data-stu-id="577ec-135">Strategic use of multiple data formats within a single data object potentially makes the data object consumable by a wider variety of drop targets than if only a single data format could be represented.</span></span>  <span data-ttu-id="577ec-136">请注意, 通常情况下, 拖动源对于可能的放置目标可以使用的数据格式是不可知的。</span><span class="sxs-lookup"><span data-stu-id="577ec-136">Note that, in general, a drag source must be agnostic about the data formats that are consumable by potential drop targets.</span></span>  
  
 <span data-ttu-id="577ec-137">下面的示例演示如何使用<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>方法将数据添加到采用多种格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-137">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a><span data-ttu-id="577ec-138">查询数据对象的可用格式</span><span class="sxs-lookup"><span data-stu-id="577ec-138">Querying a Data Object for Available Formats</span></span>  
 <span data-ttu-id="577ec-139">由于单个数据对象可以包含任意数量的数据格式, 因此数据对象包括用于检索可用数据格式列表的功能。</span><span class="sxs-lookup"><span data-stu-id="577ec-139">Because a single data object can contain an arbitrary number of data formats, data objects include facilities for retrieving a list of available data formats.</span></span>  
  
 <span data-ttu-id="577ec-140">下面的示例代码使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取一个字符串数组, 该数组表示数据对象中可用的所有数据格式 (本机和自动转换)。</span><span class="sxs-lookup"><span data-stu-id="577ec-140">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and by auto-convert).</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 <span data-ttu-id="577ec-141">有关查询数据对象以获取可用数据格式的更多代码示例, 请参阅[列出数据对象中的数据格式](how-to-list-the-data-formats-in-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="577ec-141">For more examples of code that queries a data object for available data formats, see [List the Data Formats in a Data Object](how-to-list-the-data-formats-in-a-data-object.md).</span></span>  <span data-ttu-id="577ec-142">有关查询数据对象是否存在特定数据格式的示例, 请参阅[确定数据格式是否存在于数据对象中](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)。</span><span class="sxs-lookup"><span data-stu-id="577ec-142">For examples of querying a data object for the presence of a particular data format, see [Determine if a Data Format is Present in a Data Object](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).</span></span>  
  
### <a name="retrieving-data-from-a-data-object"></a><span data-ttu-id="577ec-143">从数据对象检索数据</span><span class="sxs-lookup"><span data-stu-id="577ec-143">Retrieving Data from a Data Object</span></span>  
 <span data-ttu-id="577ec-144">从数据对象中检索特定格式的数据只需调用其中一个<xref:System.Windows.DataObject.GetData%2A>方法并指定所需的数据格式即可。</span><span class="sxs-lookup"><span data-stu-id="577ec-144">Retrieving data from a data object in a particular format simply involves calling one of the <xref:System.Windows.DataObject.GetData%2A> methods and specifying the desired data format.</span></span>  <span data-ttu-id="577ec-145">其中一种方法可用于检查是否存在特定的数据格式。 <xref:System.Windows.DataObject.GetDataPresent%2A></span><span class="sxs-lookup"><span data-stu-id="577ec-145">One of the <xref:System.Windows.DataObject.GetDataPresent%2A> methods can be used to check for the presence of a particular data format.</span></span>  <span data-ttu-id="577ec-146"><xref:System.Windows.DataObject.GetData%2A>返回中<xref:System.Object>的数据; 根据数据格式, 此对象可强制转换为特定于类型的容器。</span><span class="sxs-lookup"><span data-stu-id="577ec-146"><xref:System.Windows.DataObject.GetData%2A> returns the data in an <xref:System.Object>; depending on the data format, this object can be cast to a type-specific container.</span></span>  
  
 <span data-ttu-id="577ec-147">下面的示例代码使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>重载来检查指定的数据格式 (本机或自动转换) 是否可用。</span><span class="sxs-lookup"><span data-stu-id="577ec-147">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to check if a specified data format is available (native or by auto-convert).</span></span> <span data-ttu-id="577ec-148">如果指定的格式可用, 则该示例使用<xref:System.Windows.DataObject.GetData%28System.String%29>方法检索数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-148">If the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 <span data-ttu-id="577ec-149">有关从数据对象中检索数据的更多代码示例, 请参阅[以特定数据格式检索数据](how-to-retrieve-data-in-a-particular-data-format.md)。</span><span class="sxs-lookup"><span data-stu-id="577ec-149">For more examples of code that retrieves data from a data object, see [Retrieve Data in a Particular Data Format](how-to-retrieve-data-in-a-particular-data-format.md).</span></span>  
  
### <a name="removing-data-from-a-data-object"></a><span data-ttu-id="577ec-150">从数据对象中删除数据</span><span class="sxs-lookup"><span data-stu-id="577ec-150">Removing Data From a Data Object</span></span>  
 <span data-ttu-id="577ec-151">不能直接从数据对象中删除数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-151">Data cannot be directly removed from a data object.</span></span>  <span data-ttu-id="577ec-152">若要有效地从数据对象中删除数据, 请执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="577ec-152">To effectively remove data from a data object, follow these steps:</span></span>  
  
1. <span data-ttu-id="577ec-153">创建一个新的数据对象, 该对象将只包含您要保留的数据。</span><span class="sxs-lookup"><span data-stu-id="577ec-153">Create a new data object that will contain only the data you want to retain.</span></span>  
  
2. <span data-ttu-id="577ec-154">将所需的数据从旧的数据对象复制到新的数据对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-154">"Copy" the desired data from the old data object to the new data object.</span></span>  <span data-ttu-id="577ec-155">若要复制数据, 请使用一<xref:System.Windows.DataObject.GetData%2A>种方法来<xref:System.Object>检索包含原始数据的, <xref:System.Windows.DataObject.SetData%2A>然后使用其中一种方法将数据添加到新的数据对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-155">To copy the data, use one of the <xref:System.Windows.DataObject.GetData%2A> methods to retrieve an <xref:System.Object> that contains the raw data, and then use one of the <xref:System.Windows.DataObject.SetData%2A> methods to add the data to the new data object.</span></span>  
  
3. <span data-ttu-id="577ec-156">将旧数据对象替换为新对象。</span><span class="sxs-lookup"><span data-stu-id="577ec-156">Replace the old data object with the new one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="577ec-157"><xref:System.Windows.DataObject.SetData%2A>方法只将数据添加到数据对象; 不替换数据, 即使数据和数据格式与上一个调用完全相同。</span><span class="sxs-lookup"><span data-stu-id="577ec-157">The <xref:System.Windows.DataObject.SetData%2A> methods only add data to a data object; they do not replace data, even if the data and data format are exactly the same as a previous call.</span></span> <span data-ttu-id="577ec-158">为<xref:System.Windows.DataObject.SetData%2A>相同的数据和数据格式调用两次会导致数据/数据格式在数据对象中出现两次。</span><span class="sxs-lookup"><span data-stu-id="577ec-158">Calling <xref:System.Windows.DataObject.SetData%2A> twice for the same data and data format will result in the data/data format being present twice in the data object.</span></span>
