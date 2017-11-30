---
title: "枚举格式字符串"
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
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0992d8591711073f9094c29fad980a8e652e686
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="840b0-102">枚举格式字符串</span><span class="sxs-lookup"><span data-stu-id="840b0-102">Enumeration Format Strings</span></span>
<span data-ttu-id="840b0-103">你可以使用<xref:System.Enum.ToString%2A?displayProperty=nameWithType>方法来创建新的字符串对象，表示数字、 十六进制、 或的枚举成员的字符串值。</span><span class="sxs-lookup"><span data-stu-id="840b0-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="840b0-104">此方法采用枚举格式设置字符串之一来指定要返回的值。</span><span class="sxs-lookup"><span data-stu-id="840b0-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>  
  
 <span data-ttu-id="840b0-105">下表列出了枚举格式设置字符串和它们返回的值。</span><span class="sxs-lookup"><span data-stu-id="840b0-105">The following table lists the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="840b0-106">这些格式说明符不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="840b0-106">These format specifiers are not case-sensitive.</span></span>  
  
| <span data-ttu-id="840b0-107">格式字符串</span><span class="sxs-lookup"><span data-stu-id="840b0-107">Format string</span></span> | <span data-ttu-id="840b0-108">结果</span><span class="sxs-lookup"><span data-stu-id="840b0-108">Result</span></span> |  
| ------------- | ------ |  
| <span data-ttu-id="840b0-109">G 或 g</span><span class="sxs-lookup"><span data-stu-id="840b0-109">G or g</span></span> | <span data-ttu-id="840b0-110">如有可能，将枚举项显示为字符串值，否则显示当前实例的整数值。</span><span class="sxs-lookup"><span data-stu-id="840b0-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="840b0-111">如果枚举使用 **Flags** 属性集进行定义，则每个有效项的字符串值会连接在一起（以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="840b0-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="840b0-112">如果未设置 **Flags** 属性，则将无效值显示为数字项。</span><span class="sxs-lookup"><span data-stu-id="840b0-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="840b0-113">下面的示例演示 G 格式说明符。</span><span class="sxs-lookup"><span data-stu-id="840b0-113">The following example illustrates the G format specifier.</span></span><br><br><span data-ttu-id="840b0-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="840b0-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span></span> |  
| <span data-ttu-id="840b0-115">F 或 f</span><span class="sxs-lookup"><span data-stu-id="840b0-115">F or f</span></span> | <span data-ttu-id="840b0-116">如有可能，将枚举项显示为字符串值。</span><span class="sxs-lookup"><span data-stu-id="840b0-116">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="840b0-117">如果值可以完全显示为枚举中项的总和（即使未提供 **Flags** 属性），则每个有效项的字符串值会连接在一起（以逗号分隔）。</span><span class="sxs-lookup"><span data-stu-id="840b0-117">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="840b0-118">如果值不能由枚举项完全确定，则值会格式化为整数值。</span><span class="sxs-lookup"><span data-stu-id="840b0-118">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="840b0-119">下面的示例演示 F 格式说明符。</span><span class="sxs-lookup"><span data-stu-id="840b0-119">The following example illustrates the F format specifier.</span></span><br><br><span data-ttu-id="840b0-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="840b0-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span></span> |  
| <span data-ttu-id="840b0-121">D 或 d</span><span class="sxs-lookup"><span data-stu-id="840b0-121">D or d</span></span> | <span data-ttu-id="840b0-122">以尽可能短的表示形式将枚举项显示为整数值。</span><span class="sxs-lookup"><span data-stu-id="840b0-122">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="840b0-123">下面的示例演示 D 格式说明符。</span><span class="sxs-lookup"><span data-stu-id="840b0-123">The following example illustrates the D format specifier.</span></span><br><br><span data-ttu-id="840b0-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="840b0-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span></span> |  
| <span data-ttu-id="840b0-125">X 或 x</span><span class="sxs-lookup"><span data-stu-id="840b0-125">X or x</span></span> | <span data-ttu-id="840b0-126">将枚举项显示为十六进制值。</span><span class="sxs-lookup"><span data-stu-id="840b0-126">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="840b0-127">值在显示时根据需要带有前导零，以确保值的长度最小为八位数字。</span><span class="sxs-lookup"><span data-stu-id="840b0-127">The value is represented with leading zeros as necessary, to ensure that the value is a minimum eight digits in length.</span></span> <span data-ttu-id="840b0-128">下面的示例演示 X 格式说明符。</span><span class="sxs-lookup"><span data-stu-id="840b0-128">The following example illustrates the X format specifier.</span></span><br /><br /> <span data-ttu-id="840b0-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="840b0-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span></span> |  
  
## <a name="example"></a><span data-ttu-id="840b0-130">示例</span><span class="sxs-lookup"><span data-stu-id="840b0-130">Example</span></span>  
 <span data-ttu-id="840b0-131">下面的示例定义一个名为 `Colors` 的枚举，它由三个项组成：`Red`、`Blue` 和 `Green`。</span><span class="sxs-lookup"><span data-stu-id="840b0-131">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 <span data-ttu-id="840b0-132">定义该枚举之后，可以按以下方式声明实例。</span><span class="sxs-lookup"><span data-stu-id="840b0-132">After the enumeration is defined, an instance can be declared in the following manner.</span></span>  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 <span data-ttu-id="840b0-133">`Color.ToString(System.String)` 方法随后可以用于以不同方式显示枚举值（具体取决于传递给它的格式说明符）。</span><span class="sxs-lookup"><span data-stu-id="840b0-133">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="840b0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="840b0-134">See Also</span></span>  
 [<span data-ttu-id="840b0-135">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="840b0-135">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
