---
title: "在 .NET Framework 中操作字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], manipulating
- manipulating strings
ms.assetid: d4568ff3-9f83-4549-acd8-47aec2194ac0
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b1db77672928ebf4a03b69b4bef1af80f04124b5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="manipulating-strings-in-net"></a><span data-ttu-id="d71a7-102">控制 .NET 中的字符串</span><span class="sxs-lookup"><span data-stu-id="d71a7-102">Manipulating Strings in .NET</span></span>
<span data-ttu-id="d71a7-103">.NET 提供了一组广泛的例程，使你可以高效地创建、比较和修改字符串，以及快速分析大量文本和数据以搜索、删除和替换文本模式。</span><span class="sxs-lookup"><span data-stu-id="d71a7-103">.NET provides an extensive set of routines that enable you to efficiently create, compare, and modify strings as well as rapidly parse large amounts of text and data to search for, remove, and replace text patterns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d71a7-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d71a7-104">In This Section</span></span>  
 [<span data-ttu-id="d71a7-105">有关使用字符串的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d71a7-105">Best Practices for Using Strings</span></span>](../../../docs/standard/base-types/best-practices-strings.md)  
 <span data-ttu-id="d71a7-106">介绍了 .NET 中的字符串排序、比较和大小写转换方法，提出了有关如何选择字符串处理方法的建议。</span><span class="sxs-lookup"><span data-stu-id="d71a7-106">Examines string-sorting, comparison, and casing methods in .NET, and provides recommendations for selecting a string-handling method .</span></span>  
  
 [<span data-ttu-id="d71a7-107">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="d71a7-107">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="d71a7-108">详细介绍了 .NET 正则表达式，包括语言元素、正则表达式行为和示例。</span><span class="sxs-lookup"><span data-stu-id="d71a7-108">Provides detailed information about .NET regular expressions, including language elements, regular expression behavior, and examples.</span></span>  
  
 [<span data-ttu-id="d71a7-109">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="d71a7-109">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 <span data-ttu-id="d71a7-110">介绍了 <xref:System.String?displayProperty=nameWithType> 和 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 类提供的字符串操作，包括通过字节数组新建字符串、比较字符串值和修改现有字符串。</span><span class="sxs-lookup"><span data-stu-id="d71a7-110">Describes string operations provided by the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes, including creating new strings from arrays of bytes, comparing string values, and modifying existing strings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d71a7-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="d71a7-111">Related Sections</span></span>  
 [<span data-ttu-id="d71a7-112">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="d71a7-112">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="d71a7-113">介绍了使用 .NET 转换类型的技术和规则。</span><span class="sxs-lookup"><span data-stu-id="d71a7-113">Explains the techniques and rules used to convert types using .NET.</span></span>  
  
 [<span data-ttu-id="d71a7-114">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="d71a7-114">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="d71a7-115">介绍了如何使用基类库实现格式设置、如何设置数字类型的格式、如何设置字符串类型的格式，以及如何针对特定区域性设置格式。</span><span class="sxs-lookup"><span data-stu-id="d71a7-115">Provides how to use the base class library to implement formatting, how to format numeric types, how to format string types, and how to format for a specific culture.</span></span>  
  
 [<span data-ttu-id="d71a7-116">Parsing Strings</span><span class="sxs-lookup"><span data-stu-id="d71a7-116">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 <span data-ttu-id="d71a7-117">描述如何将对象初始化为这些对象的字符串表示形式所描述的值。</span><span class="sxs-lookup"><span data-stu-id="d71a7-117">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="d71a7-118">分析是格式化的反向操作。</span><span class="sxs-lookup"><span data-stu-id="d71a7-118">Parsing is the inverse operation of formatting.</span></span>
