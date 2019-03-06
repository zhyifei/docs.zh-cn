---
title: 如何：创建数据对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: f7bdfbf3dba0c700513348195c1d031d4c2c8b65
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370587"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="b470a-102">如何：创建数据对象</span><span class="sxs-lookup"><span data-stu-id="b470a-102">How to: Create a Data Object</span></span>
<span data-ttu-id="b470a-103">下面的示例演示创建数据对象使用的构造函数提供的各种方式<xref:System.Windows.DataObject>类。</span><span class="sxs-lookup"><span data-stu-id="b470a-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b470a-104">示例</span><span class="sxs-lookup"><span data-stu-id="b470a-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b470a-105">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-105">Description</span></span>  
 <span data-ttu-id="b470a-106">下面的代码示例创建一个新的数据对象，并使用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) 来初始化数据对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="b470a-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="b470a-107">在这种情况下，根据存储的数据类型自动确定适当的数据格式，且默认情况下允许存储的数据自动转换。</span><span class="sxs-lookup"><span data-stu-id="b470a-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-108">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="b470a-109">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-109">Description</span></span>  
 <span data-ttu-id="b470a-110">下面的代码示例是代码的上面所示的精简的版本。</span><span class="sxs-lookup"><span data-stu-id="b470a-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-111">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b470a-112">示例</span><span class="sxs-lookup"><span data-stu-id="b470a-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b470a-113">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-113">Description</span></span>  
 <span data-ttu-id="b470a-114">下面的代码示例创建一个新的数据对象，并使用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="b470a-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b470a-115">一个字符串; 在这种情况下指定的数据格式<xref:System.Windows.DataFormats>类提供了一组预定义的类型字符串。</span><span class="sxs-lookup"><span data-stu-id="b470a-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="b470a-116">默认情况下，允许存储的数据将自动转换。</span><span class="sxs-lookup"><span data-stu-id="b470a-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-117">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="b470a-118">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-118">Description</span></span>  
 <span data-ttu-id="b470a-119">下面的代码示例是代码的上面所示的精简的版本。</span><span class="sxs-lookup"><span data-stu-id="b470a-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-120">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b470a-121">示例</span><span class="sxs-lookup"><span data-stu-id="b470a-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b470a-122">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-122">Description</span></span>  
 <span data-ttu-id="b470a-123">下面的代码示例创建一个新的数据对象，并使用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%2A>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="b470a-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b470a-124">指定数据格式在这种情况下<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="b470a-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="b470a-125">默认情况下，允许存储的数据将自动转换。</span><span class="sxs-lookup"><span data-stu-id="b470a-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-126">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="b470a-127">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-127">Description</span></span>  
 <span data-ttu-id="b470a-128">下面的代码示例是代码的上面所示的精简的版本。</span><span class="sxs-lookup"><span data-stu-id="b470a-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-129">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b470a-130">示例</span><span class="sxs-lookup"><span data-stu-id="b470a-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b470a-131">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-131">Description</span></span>  
 <span data-ttu-id="b470a-132">下面的代码示例创建一个新的数据对象，并使用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="b470a-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b470a-133">一个字符串; 在这种情况下指定的数据格式<xref:System.Windows.DataFormats>类提供了一组预定义的类型字符串。</span><span class="sxs-lookup"><span data-stu-id="b470a-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="b470a-134">此特定构造函数重载允许调用方指定是否允许将自动转换。</span><span class="sxs-lookup"><span data-stu-id="b470a-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-135">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="b470a-136">描述</span><span class="sxs-lookup"><span data-stu-id="b470a-136">Description</span></span>  
 <span data-ttu-id="b470a-137">下面的代码示例是代码的上面所示的精简的版本。</span><span class="sxs-lookup"><span data-stu-id="b470a-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b470a-138">代码</span><span class="sxs-lookup"><span data-stu-id="b470a-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="b470a-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b470a-139">See also</span></span>
- <xref:System.Windows.IDataObject>
