---
title: "检索存储在特性中的信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="fd424-102">检索存储在特性中的信息</span><span class="sxs-lookup"><span data-stu-id="fd424-102">Retrieving Information Stored in Attributes</span></span>
<span data-ttu-id="fd424-103">检索的自定义特性是一个简单的过程。</span><span class="sxs-lookup"><span data-stu-id="fd424-103">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="fd424-104">首先，声明你想要检索的属性的实例。</span><span class="sxs-lookup"><span data-stu-id="fd424-104">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="fd424-105">然后，使用<xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>方法以初始化为你想要检索的属性值的新属性。</span><span class="sxs-lookup"><span data-stu-id="fd424-105">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="fd424-106">后在初始化新的属性时，只需使用其属性来获取值。</span><span class="sxs-lookup"><span data-stu-id="fd424-106">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd424-107">本主题介绍如何检索加载到执行上下文的代码中的特性。</span><span class="sxs-lookup"><span data-stu-id="fd424-107">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="fd424-108">若要检索的代码加载到只反射上下文的特性，必须使用<xref:System.Reflection.CustomAttributeData>类，如下所示[如何： 将程序集加载到 Reflection-Only 上下文](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。</span><span class="sxs-lookup"><span data-stu-id="fd424-108">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="fd424-109">本部分介绍了以下方式来检索属性：</span><span class="sxs-lookup"><span data-stu-id="fd424-109">This section describes the following ways to retrieve attributes:</span></span>  
  
-   [<span data-ttu-id="fd424-110">检索属性的一个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-110">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
-   [<span data-ttu-id="fd424-111">检索属性应用于同一范围内的多个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-111">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [<span data-ttu-id="fd424-112">检索应用到不同的作用域的属性的多个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-112">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="fd424-113">检索属性的一个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-113">Retrieving a Single Instance of an Attribute</span></span>  
 <span data-ttu-id="fd424-114">在下面的示例中， `DeveloperAttribute` （上一节中所述） 应用于`MainApp`类级别上的类。</span><span class="sxs-lookup"><span data-stu-id="fd424-114">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="fd424-115">`GetAttribute`方法使用**GetCustomAttribute**检索中存储的值`DeveloperAttribute`之前向控制台显示它们的类级别上。</span><span class="sxs-lookup"><span data-stu-id="fd424-115">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="fd424-116">此程序显示以下文本时执行。</span><span class="sxs-lookup"><span data-stu-id="fd424-116">This program displays the following text when executed.</span></span>  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="fd424-117">如果未找到该属性， **GetCustomAttribute**方法初始化`MyAttribute`为 null 值。</span><span class="sxs-lookup"><span data-stu-id="fd424-117">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="fd424-118">此示例检查`MyAttribute`的此类实例，并通知用户，如果不找到任何属性。</span><span class="sxs-lookup"><span data-stu-id="fd424-118">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="fd424-119">如果`DeveloperAttribute`找不到在类范围中，向控制台显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="fd424-119">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```  
The attribute was not found.   
```  
  
 <span data-ttu-id="fd424-120">此示例假定属性定义是在当前命名空间。</span><span class="sxs-lookup"><span data-stu-id="fd424-120">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="fd424-121">请记住要导入的属性定义驻留如果它不在当前命名空间的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fd424-121">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="fd424-122">检索属性应用于同一范围内的多个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-122">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  
 <span data-ttu-id="fd424-123">在前面的示例中，要检查的类和要查找的特定属性将传递到<xref:System.Attribute.GetCustomAttribute%2A>。</span><span class="sxs-lookup"><span data-stu-id="fd424-123">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="fd424-124">如果也只在类级别上应用属性的一个实例，该代码将运行。</span><span class="sxs-lookup"><span data-stu-id="fd424-124">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="fd424-125">但是，如果属性的多个实例应用于相同的类级别， **GetCustomAttribute**方法未检索所有信息。</span><span class="sxs-lookup"><span data-stu-id="fd424-125">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="fd424-126">在其中将同一特性的多个实例应用于同一作用域的情况下，你可以使用<xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>放置到一个数组的所有实例的属性。</span><span class="sxs-lookup"><span data-stu-id="fd424-126">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="fd424-127">例如，如果两个实例的`DeveloperAttribute`同一类中，在类级别上应用`GetAttribute`方法可以修改，以显示在这两个属性中找到的信息。</span><span class="sxs-lookup"><span data-stu-id="fd424-127">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="fd424-128">请记住，在同一级别中，将多个属性必须与定义的属性**AllowMultiple**属性设置为**true**中<xref:System.AttributeUsageAttribute>。</span><span class="sxs-lookup"><span data-stu-id="fd424-128">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="fd424-129">下面的代码示例演示如何使用**GetCustomAttributes**方法来创建一个数组，其中引用的所有实例`DeveloperAttribute`在任何给定类。</span><span class="sxs-lookup"><span data-stu-id="fd424-129">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="fd424-130">所有属性的值将显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="fd424-130">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="fd424-131">如果找不到任何属性，该代码将提醒用户。</span><span class="sxs-lookup"><span data-stu-id="fd424-131">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="fd424-132">否则，在两个实例中包含的信息`DeveloperAttribute`显示。</span><span class="sxs-lookup"><span data-stu-id="fd424-132">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="fd424-133">检索应用到不同的作用域的属性的多个实例</span><span class="sxs-lookup"><span data-stu-id="fd424-133">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  
 <span data-ttu-id="fd424-134"><xref:System.Attribute.GetCustomAttributes%2A>和<xref:System.Attribute.GetCustomAttribute%2A>方法不会搜索整个类和在该类中返回的属性的所有实例。</span><span class="sxs-lookup"><span data-stu-id="fd424-134">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="fd424-135">相反，它们一次搜索只能有一个指定的方法或成员。</span><span class="sxs-lookup"><span data-stu-id="fd424-135">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="fd424-136">如果类具有相同的属性应用于每个成员，并且你想要检索中应用于这些成员的所有属性的值，则必须为每个方法或成员单独向**GetCustomAttributes**和**GetCustomAttribute**。</span><span class="sxs-lookup"><span data-stu-id="fd424-136">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="fd424-137">下面的代码示例采用类作为一个参数，并搜索`DeveloperAttribute`（已定义以前） 和该类的每个单个方法的类级别上。</span><span class="sxs-lookup"><span data-stu-id="fd424-137">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="fd424-138">如果没有实例`DeveloperAttribute`上的方法级别或类级别上，找到`GetAttribute`方法，则通知用户，未找到特性，并显示方法或不包含属性的类的名称。</span><span class="sxs-lookup"><span data-stu-id="fd424-138">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="fd424-139">如果找到一个属性， `Name`， `Level`，和`Reviewed`字段显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="fd424-139">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="fd424-140">你可以使用的成员<xref:System.Type>类，以传递的类中获取的各个方法和成员。</span><span class="sxs-lookup"><span data-stu-id="fd424-140">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="fd424-141">该示例首先查询**类型**对象以获取类级别的特性信息。</span><span class="sxs-lookup"><span data-stu-id="fd424-141">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="fd424-142">接下来，它使用<xref:System.Type.GetMethods%2A?displayProperty=nameWithType>将转换为数组的所有方法的实例放<xref:System.Reflection.MemberInfo?displayProperty=nameWithType>要检索的方法级别的属性信息的对象。</span><span class="sxs-lookup"><span data-stu-id="fd424-142">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="fd424-143">你还可以使用<xref:System.Type.GetProperties%2A?displayProperty=nameWithType>方法来检查在属性级别上的属性或<xref:System.Type.GetConstructors%2A?displayProperty=nameWithType>要检查的构造函数级别上的特性。</span><span class="sxs-lookup"><span data-stu-id="fd424-143">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd424-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd424-144">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fd424-145">特性</span><span class="sxs-lookup"><span data-stu-id="fd424-145">Attributes</span></span>](../../../docs/standard/attributes/index.md)
