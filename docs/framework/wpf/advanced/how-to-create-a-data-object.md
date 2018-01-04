---
title: "如何：创建数据对象"
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
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="d0015-102">如何：创建数据对象</span><span class="sxs-lookup"><span data-stu-id="d0015-102">How to: Create a Data Object</span></span>
<span data-ttu-id="d0015-103">下面的示例演示多种创建使用提供的构造函数的数据对象<xref:System.Windows.DataObject>类。</span><span class="sxs-lookup"><span data-stu-id="d0015-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0015-104">示例</span><span class="sxs-lookup"><span data-stu-id="d0015-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0015-105">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-105">Description</span></span>  
 <span data-ttu-id="d0015-106">下面的代码示例创建一个新的数据对象，并利用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) 以初始化数据对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0015-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="d0015-107">在这种情况下，根据所存储的数据类型，自动确定相应的数据格式，默认情况下允许存储的数据自动转换。</span><span class="sxs-lookup"><span data-stu-id="d0015-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-108">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="d0015-109">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-109">Description</span></span>  
 <span data-ttu-id="d0015-110">下面的代码示例是代码的上面显示的压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="d0015-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-111">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="d0015-112">示例</span><span class="sxs-lookup"><span data-stu-id="d0015-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0015-113">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-113">Description</span></span>  
 <span data-ttu-id="d0015-114">下面的代码示例创建一个新的数据对象，并利用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="d0015-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="d0015-115">字符串; 在这种情况下指定的数据格式<xref:System.Windows.DataFormats>类提供一组预定义的类型字符串。</span><span class="sxs-lookup"><span data-stu-id="d0015-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="d0015-116">默认情况下，允许存储的数据将自动转换。</span><span class="sxs-lookup"><span data-stu-id="d0015-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-117">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="d0015-118">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-118">Description</span></span>  
 <span data-ttu-id="d0015-119">下面的代码示例是代码的上面显示的压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="d0015-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-120">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="d0015-121">示例</span><span class="sxs-lookup"><span data-stu-id="d0015-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0015-122">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-122">Description</span></span>  
 <span data-ttu-id="d0015-123">下面的代码示例创建一个新的数据对象，并利用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%2A>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="d0015-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="d0015-124">指定数据格式在这种情况下<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="d0015-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="d0015-125">默认情况下，允许存储的数据将自动转换。</span><span class="sxs-lookup"><span data-stu-id="d0015-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-126">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="d0015-127">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-127">Description</span></span>  
 <span data-ttu-id="d0015-128">下面的代码示例是代码的上面显示的压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="d0015-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-129">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="d0015-130">示例</span><span class="sxs-lookup"><span data-stu-id="d0015-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d0015-131">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-131">Description</span></span>  
 <span data-ttu-id="d0015-132">下面的代码示例创建一个新的数据对象，并利用重载的构造函数之一 (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) 来初始化具有一个字符串，指定的数据格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="d0015-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="d0015-133">字符串; 在这种情况下指定的数据格式<xref:System.Windows.DataFormats>类提供一组预定义的类型字符串。</span><span class="sxs-lookup"><span data-stu-id="d0015-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="d0015-134">此特定构造函数重载使调用方指定是否允许将自动转换。</span><span class="sxs-lookup"><span data-stu-id="d0015-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-135">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="d0015-136">描述</span><span class="sxs-lookup"><span data-stu-id="d0015-136">Description</span></span>  
 <span data-ttu-id="d0015-137">下面的代码示例是代码的上面显示的压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="d0015-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d0015-138">代码</span><span class="sxs-lookup"><span data-stu-id="d0015-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="d0015-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0015-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>
