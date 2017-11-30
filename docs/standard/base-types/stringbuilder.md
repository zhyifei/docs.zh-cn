---
title: "在.NET 中使用 StringBuilder 类"
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
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a><span data-ttu-id="25349-102">在.NET 中使用 StringBuilder 类</span><span class="sxs-lookup"><span data-stu-id="25349-102">Using the StringBuilder Class in .NET</span></span>
<span data-ttu-id="25349-103"><xref:System.String>对象是不可变。</span><span class="sxs-lookup"><span data-stu-id="25349-103">The <xref:System.String> object is immutable.</span></span> <span data-ttu-id="25349-104">每次使用中的方法之一<xref:System.String?displayProperty=nameWithType>类，你在内存中，这就需要为该新对象的新分配的空间创建新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="25349-104">Every time you use one of the methods in the <xref:System.String?displayProperty=nameWithType> class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="25349-105">在你需要对字符串执行重复的修改的情况下，创建一个新关联的系统开销<xref:System.String>对象开销会很大。</span><span class="sxs-lookup"><span data-stu-id="25349-105">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new <xref:System.String> object can be costly.</span></span> <span data-ttu-id="25349-106"><xref:System.Text.StringBuilder?displayProperty=nameWithType>类可用于当你想要修改字符串而不创建新对象。</span><span class="sxs-lookup"><span data-stu-id="25349-106">The <xref:System.Text.StringBuilder?displayProperty=nameWithType> class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="25349-107">例如，使用<xref:System.Text.StringBuilder>串联在一起在循环中的许多字符串时，类可以提升性能。</span><span class="sxs-lookup"><span data-stu-id="25349-107">For example, using the <xref:System.Text.StringBuilder> class can boost performance when concatenating many strings together in a loop.</span></span>  
  
## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="25349-108">导入 System.Text 命名空间</span><span class="sxs-lookup"><span data-stu-id="25349-108">Importing the System.Text Namespace</span></span>  
 <span data-ttu-id="25349-109"><xref:System.Text.StringBuilder>中找到该类<xref:System.Text>命名空间。</span><span class="sxs-lookup"><span data-stu-id="25349-109">The <xref:System.Text.StringBuilder> class is found in the <xref:System.Text> namespace.</span></span>  <span data-ttu-id="25349-110">为了避免必须提供完全限定的类型名称在代码中，你可以导入<xref:System.Text>命名空间：</span><span class="sxs-lookup"><span data-stu-id="25349-110">To avoid having to provide a fully qualified type name in your code,  you can import the <xref:System.Text> namespace:</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="25349-111">实例化 StringBuilder 对象</span><span class="sxs-lookup"><span data-stu-id="25349-111">Instantiating a StringBuilder Object</span></span>  
 <span data-ttu-id="25349-112">你可以创建的新实例<xref:System.Text.StringBuilder>用一个重载构造函数方法，初始化变量，如下面的示例中所示的类。</span><span class="sxs-lookup"><span data-stu-id="25349-112">You can create a new instance of the <xref:System.Text.StringBuilder> class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="25349-113">设置容量和长度</span><span class="sxs-lookup"><span data-stu-id="25349-113">Setting the Capacity and Length</span></span>  
 <span data-ttu-id="25349-114">尽管<xref:System.Text.StringBuilder>是动态对象，您可以展开它所封装的字符串中的字符数可以指定的最大可保留的字符数的值。</span><span class="sxs-lookup"><span data-stu-id="25349-114">Although the <xref:System.Text.StringBuilder> is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="25349-115">此值称为该对象的容量，不应为字符串的长度相混淆，当前<xref:System.Text.StringBuilder>保存。</span><span class="sxs-lookup"><span data-stu-id="25349-115">This value is called the capacity of the object and should not be confused with the length of the string that the current <xref:System.Text.StringBuilder> holds.</span></span> <span data-ttu-id="25349-116">例如，你可能创建的新实例<xref:System.Text.StringBuilder>与字符串"Hello"，长度为 5，和你的类可能会指定该对象具有的最大容量为 25。</span><span class="sxs-lookup"><span data-stu-id="25349-116">For example, you might create a new instance of the <xref:System.Text.StringBuilder> class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="25349-117">当修改<xref:System.Text.StringBuilder>，它不重新分配大小为自身直到达到容量。</span><span class="sxs-lookup"><span data-stu-id="25349-117">When you modify the <xref:System.Text.StringBuilder>, it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="25349-118">当达到容量时，将自动分配新的空间且容量翻倍。</span><span class="sxs-lookup"><span data-stu-id="25349-118">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="25349-119">你可以指定的容量<xref:System.Text.StringBuilder>类使用重载构造函数之一。</span><span class="sxs-lookup"><span data-stu-id="25349-119">You can specify the capacity of the <xref:System.Text.StringBuilder> class using one of the overloaded constructors.</span></span> <span data-ttu-id="25349-120">下面的示例指定可以将 `MyStringBuilder` 对象增加到最多 25 个空间。</span><span class="sxs-lookup"><span data-stu-id="25349-120">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 <span data-ttu-id="25349-121">此外，你可以使用读/写<xref:System.Text.StringBuilder.Capacity%2A>属性来设置你的对象的最大长度。</span><span class="sxs-lookup"><span data-stu-id="25349-121">Additionally, you can use the read/write <xref:System.Text.StringBuilder.Capacity%2A> property to set the maximum length of your object.</span></span> <span data-ttu-id="25349-122">下面的示例使用 **Capacity** 属性来定义对象的最大长度。</span><span class="sxs-lookup"><span data-stu-id="25349-122">The following example uses the **Capacity** property to define the maximum object length.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <span data-ttu-id="25349-123"><xref:System.Text.StringBuilder.EnsureCapacity%2A>方法可以用于检查当前的容量**StringBuilder**。</span><span class="sxs-lookup"><span data-stu-id="25349-123">The <xref:System.Text.StringBuilder.EnsureCapacity%2A> method can be used to check the capacity of the current **StringBuilder**.</span></span> <span data-ttu-id="25349-124">如果容量大于传递的值，则不进行任何更改；但是，如果容量小于传递的值，则会更改当前的容量以使其与传递的值匹配。</span><span class="sxs-lookup"><span data-stu-id="25349-124">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>  
  
 <span data-ttu-id="25349-125"><xref:System.Text.StringBuilder.Length%2A>属性还可以查看或设置。</span><span class="sxs-lookup"><span data-stu-id="25349-125">The <xref:System.Text.StringBuilder.Length%2A> property can also be viewed or set.</span></span> <span data-ttu-id="25349-126">如果将 **Length** 属性设置为大于 **Capacity** 属性的值，则自动将 **Capacity** 属性更改为与 **Length** 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="25349-126">If you set the **Length** property to a value that is greater than the **Capacity** property, the **Capacity** property is automatically changed to the same value as the **Length** property.</span></span> <span data-ttu-id="25349-127">如果将 **Length** 属性设置为小于当前 **StringBuilder** 对象内的字符串长度的值，则会缩短该字符串。</span><span class="sxs-lookup"><span data-stu-id="25349-127">Setting the **Length** property to a value that is less than the length of the string within the current **StringBuilder** shortens the string.</span></span>  
  
## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="25349-128">修改 StringBuilder 字符串</span><span class="sxs-lookup"><span data-stu-id="25349-128">Modifying the StringBuilder String</span></span>  
 <span data-ttu-id="25349-129">下表列出了可用于修改 **StringBuilder** 内容的方法。</span><span class="sxs-lookup"><span data-stu-id="25349-129">The following table lists the methods you can use to modify the contents of a **StringBuilder**.</span></span>  
  
|<span data-ttu-id="25349-130">方法名称</span><span class="sxs-lookup"><span data-stu-id="25349-130">Method name</span></span>|<span data-ttu-id="25349-131">使用</span><span class="sxs-lookup"><span data-stu-id="25349-131">Use</span></span>|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|<span data-ttu-id="25349-132">将信息追加到当前 **StringBuilder** 的末尾。</span><span class="sxs-lookup"><span data-stu-id="25349-132">Appends information to the end of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<span data-ttu-id="25349-133">用带格式文本替换字符串中传递的格式说明符。</span><span class="sxs-lookup"><span data-stu-id="25349-133">Replaces a format specifier passed in a string with formatted text.</span></span>|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="25349-134">将字符串或对象插入到当前 **StringBuilder** 的指定索引中。</span><span class="sxs-lookup"><span data-stu-id="25349-134">Inserts a string or object into the specified index of the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="25349-135">从当前 **StringBuilder** 中删除指定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="25349-135">Removes a specified number of characters from the current **StringBuilder**.</span></span>|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|<span data-ttu-id="25349-136">替换指定索引处的指定字符。</span><span class="sxs-lookup"><span data-stu-id="25349-136">Replaces a specified character at a specified index.</span></span>|  
  
### <a name="append"></a><span data-ttu-id="25349-137">追加</span><span class="sxs-lookup"><span data-stu-id="25349-137">Append</span></span>  
 <span data-ttu-id="25349-138">**追加**方法可以用于将文本或对象的字符串表示方法添加到表示由当前的字符串的末尾**StringBuilder**。</span><span class="sxs-lookup"><span data-stu-id="25349-138">The **Append** method can be used to add text or a string representation of an object to the end of a string represented by the current **StringBuilder**.</span></span> <span data-ttu-id="25349-139">下面的示例将 **StringBuilder** 对象初始化为“Hello World”，然后将一些文本追加到该对象的末尾。</span><span class="sxs-lookup"><span data-stu-id="25349-139">The following example initializes a **StringBuilder** to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="25349-140">将根据需要自动分配空间。</span><span class="sxs-lookup"><span data-stu-id="25349-140">Space is allocated automatically as needed.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a><span data-ttu-id="25349-141">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="25349-141">AppendFormat</span></span>  
 <span data-ttu-id="25349-142"><xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>方法将文本添加到末尾<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="25349-142">The <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> method adds text to the end of the <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="25349-143">它支持复合格式设置功能 (有关详细信息，请参阅[复合格式设置](../../../docs/standard/base-types/composite-formatting.md)) 通过调用<xref:System.IFormattable>实现或多个要设置格式的对象。</span><span class="sxs-lookup"><span data-stu-id="25349-143">It supports the composite formatting feature (for more information, see [Composite Formatting](../../../docs/standard/base-types/composite-formatting.md)) by calling the <xref:System.IFormattable> implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="25349-144">因此，它接受数字、日期和时间以及枚举值的标准格式字符串、数字以及日期和时间值的自定义格式字符串，以及为自定义类型定义的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="25349-144">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="25349-145">（有关格式化的信息，请参阅[格式设置类型](../../../docs/standard/base-types/formatting-types.md)。）此方法可用于自定义变量的格式和追加到这些值<xref:System.Text.StringBuilder>。</span><span class="sxs-lookup"><span data-stu-id="25349-145">(For information about formatting, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).) You can use this method to customize the format of variables and append those values to a <xref:System.Text.StringBuilder>.</span></span> <span data-ttu-id="25349-146">下面的示例使用<xref:System.Text.StringBuilder.AppendFormat%2A>方法将一个整数值格式化为货币值的末尾<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="25349-146">The following example uses the <xref:System.Text.StringBuilder.AppendFormat%2A> method to place an integer value formatted as a currency value at the end of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a><span data-ttu-id="25349-147">Insert</span><span class="sxs-lookup"><span data-stu-id="25349-147">Insert</span></span>  
 <span data-ttu-id="25349-148"><xref:System.Text.StringBuilder.Insert%2A>方法将字符串或对象添加到指定位置在当前<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="25349-148">The <xref:System.Text.StringBuilder.Insert%2A> method adds a string or object to a specified position in the current <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="25349-149">下面的示例使用此方法将一个单词插入到的第六个位置<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="25349-149">The following example uses this method to insert a word into the sixth position of a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a><span data-ttu-id="25349-150">删除</span><span class="sxs-lookup"><span data-stu-id="25349-150">Remove</span></span>  
 <span data-ttu-id="25349-151">你可以使用**删除**方法来删除指定的数目的字符从当前<xref:System.Text.StringBuilder>对象，指定从零开始的索引位置开始。</span><span class="sxs-lookup"><span data-stu-id="25349-151">You can use the **Remove** method to remove a specified number of characters from the current <xref:System.Text.StringBuilder> object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="25349-152">下面的示例使用**删除**方法缩短<xref:System.Text.StringBuilder>对象。</span><span class="sxs-lookup"><span data-stu-id="25349-152">The following example uses the **Remove** method to shorten a <xref:System.Text.StringBuilder> object.</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a><span data-ttu-id="25349-153">替换</span><span class="sxs-lookup"><span data-stu-id="25349-153">Replace</span></span>  
 <span data-ttu-id="25349-154">**替换**方法可以用于替换中的字符<xref:System.Text.StringBuilder>对象与另一个指定字符。</span><span class="sxs-lookup"><span data-stu-id="25349-154">The **Replace** method can be used to replace characters within the <xref:System.Text.StringBuilder> object with another specified character.</span></span> <span data-ttu-id="25349-155">下面的示例使用**替换**方法搜索<xref:System.Text.StringBuilder>对象的所有实例的感叹号字符 （！），并将其替换为问号字符 （？）。</span><span class="sxs-lookup"><span data-stu-id="25349-155">The following example uses the **Replace** method to search a <xref:System.Text.StringBuilder> object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="25349-156">将 StringBuilder 对象转换为字符串</span><span class="sxs-lookup"><span data-stu-id="25349-156">Converting a StringBuilder Object to a String</span></span>  
 <span data-ttu-id="25349-157">必须将转换<xref:System.Text.StringBuilder>对象传递给<xref:System.String>对象，然后可以将传递所表示的字符串<xref:System.Text.StringBuilder>对象的方法的具有<xref:System.String>参数或在用户界面中显示它。</span><span class="sxs-lookup"><span data-stu-id="25349-157">You must convert the <xref:System.Text.StringBuilder> object to a <xref:System.String> object before you can pass the string represented by the <xref:System.Text.StringBuilder> object to a method that has a <xref:System.String> parameter or display it in the user interface.</span></span> <span data-ttu-id="25349-158">通过调用来执行此转换<xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="25349-158">You do this conversion by calling the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="25349-159">下面的示例调用数量的<xref:System.Text.StringBuilder>方法，然后调用<xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType>方法以显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="25349-159">The following example calls a number of <xref:System.Text.StringBuilder> methods and then calls the <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> method to display the string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="25349-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25349-160">See Also</span></span>  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [<span data-ttu-id="25349-161">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="25349-161">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="25349-162">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="25349-162">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
