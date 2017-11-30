---
title: ".NET 中分析其他字符串"
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
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="67292-102">.NET 中分析其他字符串</span><span class="sxs-lookup"><span data-stu-id="67292-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="67292-103">除了数值和<xref:System.DateTime>字符串，还可以分析表示类型的字符串<xref:System.Char>， <xref:System.Boolean>，和<xref:System.Enum>数据类型。</span><span class="sxs-lookup"><span data-stu-id="67292-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="67292-104">Char</span><span class="sxs-lookup"><span data-stu-id="67292-104">Char</span></span>  
 <span data-ttu-id="67292-105">与 **Char** 数据类型关联的静态分析方法 可用于将包含单个字符的字符串转换为其 Unicode 值。</span><span class="sxs-lookup"><span data-stu-id="67292-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="67292-106">下面的代码示例将字符串分析为 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="67292-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="67292-107">Boolean</span><span class="sxs-lookup"><span data-stu-id="67292-107">Boolean</span></span>  
 <span data-ttu-id="67292-108">**布尔**数据类型包含**分析**可用于将转换到实际表示一个布尔值的字符串的方法**布尔**类型。</span><span class="sxs-lookup"><span data-stu-id="67292-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="67292-109">此方法不区分大小写，可以成功分析包含“True”或“False”的字符串。</span><span class="sxs-lookup"><span data-stu-id="67292-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="67292-110">**分析**与关联方法**布尔**类型还可以分析包围空格的字符串。</span><span class="sxs-lookup"><span data-stu-id="67292-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="67292-111">如果传递的其他任何字符串，<xref:System.FormatException>引发。</span><span class="sxs-lookup"><span data-stu-id="67292-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="67292-112">下面的代码示例使用**分析**方法将字符串转换为一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="67292-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="67292-113">枚举</span><span class="sxs-lookup"><span data-stu-id="67292-113">Enumeration</span></span>  
 <span data-ttu-id="67292-114">可以使用静态 **Parse** 方法将枚举类型初始化为字符串的值。</span><span class="sxs-lookup"><span data-stu-id="67292-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="67292-115">此方法接受所分析的枚举类型、 字符串进行分析、 和可选的布尔型标志，该值指示分析区分大小写。</span><span class="sxs-lookup"><span data-stu-id="67292-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="67292-116">所分析的字符串可以包含用逗号分隔的多个值，这些值前面或后面可以是一个或多个空白（也称为空格）。</span><span class="sxs-lookup"><span data-stu-id="67292-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="67292-117">当字符串包含多个值时，返回的对象的值是所有指定值通过按位 OR 运算组合的值。</span><span class="sxs-lookup"><span data-stu-id="67292-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="67292-118">下面的示例使用**分析**方法将字符串表示形式转换为一个枚举值。</span><span class="sxs-lookup"><span data-stu-id="67292-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="67292-119"><xref:System.DayOfWeek>枚举初始化为**星期四**从字符串。</span><span class="sxs-lookup"><span data-stu-id="67292-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="67292-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67292-120">See Also</span></span>  
 [<span data-ttu-id="67292-121">分析字符串</span><span class="sxs-lookup"><span data-stu-id="67292-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="67292-122">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="67292-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="67292-123">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="67292-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
