---
title: "在.NET 中创建新的字符串"
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
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="6594a-102">在.NET 中创建新的字符串</span><span class="sxs-lookup"><span data-stu-id="6594a-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="6594a-103">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]允许字符串要创建使用简单赋值，并且还重载以支持使用大量不同的参数的字符串创建的类构造函数。</span><span class="sxs-lookup"><span data-stu-id="6594a-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="6594a-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]还提供了几种方法中的<xref:System.String?displayProperty=nameWithType>创建新的字符串的类的对象，或通过组合多个字符串，字符串的数组对象。</span><span class="sxs-lookup"><span data-stu-id="6594a-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="6594a-105">通过赋值创建字符串</span><span class="sxs-lookup"><span data-stu-id="6594a-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="6594a-106">创建一个新的最简单办法<xref:System.String>对象只是将分配一个字符串赋给<xref:System.String>对象。</span><span class="sxs-lookup"><span data-stu-id="6594a-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="6594a-107">使用类构造函数创建字符串</span><span class="sxs-lookup"><span data-stu-id="6594a-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="6594a-108">你可以使用的重载<xref:System.String>类构造函数来创建从字符数组的字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="6594a-109">还可以通过将特定字符重复指定次数来创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="6594a-110">返回字符串的方法</span><span class="sxs-lookup"><span data-stu-id="6594a-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="6594a-111">下表列出了返回新字符串对象的几个有用方法。</span><span class="sxs-lookup"><span data-stu-id="6594a-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="6594a-112">方法名称</span><span class="sxs-lookup"><span data-stu-id="6594a-112">Method name</span></span>|<span data-ttu-id="6594a-113">使用</span><span class="sxs-lookup"><span data-stu-id="6594a-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="6594a-114">从一组输入对象生成格式化的字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="6594a-115">从两个或更多个字符串生成字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="6594a-116">通过合并字符串数组生成新字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="6594a-117">通过将一个字符串插入现有字符串的指定索引处生成新字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="6594a-118">将一个字符串中的指定字符复制到一个字符数组中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="6594a-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="6594a-119">格式</span><span class="sxs-lookup"><span data-stu-id="6594a-119">Format</span></span>  
 <span data-ttu-id="6594a-120">你可以使用**String.Format**方法来创建格式化的字符串并将连接字符串表示多个对象。</span><span class="sxs-lookup"><span data-stu-id="6594a-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="6594a-121">此方法自动将传递给它的任何对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="6594a-122">例如，如果你的应用程序必须显示**Int32**值和**DateTime**值对用户来说，你可以轻松地构建一个字符串，若要使用这些值表示**格式**方法。</span><span class="sxs-lookup"><span data-stu-id="6594a-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="6594a-123">有关此方法使用的格式化约定的信息，请参阅有关[复合格式化](../../../docs/standard/base-types/composite-formatting.md)的部分。</span><span class="sxs-lookup"><span data-stu-id="6594a-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="6594a-124">下面的示例使用**格式**方法来创建使用一个整数变量的字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="6594a-125">在此示例中，<xref:System.DateTime.Now%2A?displayProperty=nameWithType>以指定与当前线程关联的区域性的方式显示的当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6594a-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="6594a-126">Concat</span><span class="sxs-lookup"><span data-stu-id="6594a-126">Concat</span></span>  
 <span data-ttu-id="6594a-127">**String.Concat**方法可以用于轻松地从两个或多个现有对象创建新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="6594a-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="6594a-128">它提供了一种与语言无关的方法来连接字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="6594a-129">此方法接受任何派生自的类**System.Object**。</span><span class="sxs-lookup"><span data-stu-id="6594a-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="6594a-130">下面的示例使用两个现有字符串对象和一个分隔符创建一个字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="6594a-131">联接</span><span class="sxs-lookup"><span data-stu-id="6594a-131">Join</span></span>  
 <span data-ttu-id="6594a-132">**String.Join**方法创建新的字符串数组中的字符串和分隔符字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="6594a-133">如果想要将多个字符串连接在一起，构成一个可能由逗号分隔的列表，则此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="6594a-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="6594a-134">下面的示例使用空格来连接字符串数组。</span><span class="sxs-lookup"><span data-stu-id="6594a-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="6594a-135">Insert</span><span class="sxs-lookup"><span data-stu-id="6594a-135">Insert</span></span>  
 <span data-ttu-id="6594a-136">**String.Insert**方法通过将一个字符串插入到另一个字符串中的指定位置来创建一个新字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="6594a-137">此方法使用从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="6594a-137">This method uses a zero-based index.</span></span> <span data-ttu-id="6594a-138">下面的示例将一个字符串插入 `MyString` 的第五个索引位置，并用此值创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="6594a-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="6594a-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="6594a-139">CopyTo</span></span>  
 <span data-ttu-id="6594a-140">**String.CopyTo**方法将字符串的一部分复制到字符的数组。</span><span class="sxs-lookup"><span data-stu-id="6594a-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="6594a-141">可以同时指定字符串的开始索引和要复制的字符数。</span><span class="sxs-lookup"><span data-stu-id="6594a-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="6594a-142">此方法采用源索引、字符数组、目标索引和要复制的字符数。</span><span class="sxs-lookup"><span data-stu-id="6594a-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="6594a-143">所有索引都从零开始。</span><span class="sxs-lookup"><span data-stu-id="6594a-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="6594a-144">下面的示例使用**CopyTo**方法将单词"Hello"从字符串对象的字符复制到的字符数组的第一个索引位置。</span><span class="sxs-lookup"><span data-stu-id="6594a-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="6594a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6594a-145">See Also</span></span>  
 [<span data-ttu-id="6594a-146">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="6594a-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="6594a-147">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="6594a-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
