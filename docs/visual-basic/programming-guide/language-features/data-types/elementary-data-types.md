---
title: "基本数据类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- elementary data types
- data types [Visual Basic], elementary
ms.assetid: dfad6fe9-2da6-49a4-b0b1-2d7ae0283de5
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6d363fdd7f7f2755aec34dfe82e38d83ba6e56af
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="elementary-data-types-visual-basic"></a><span data-ttu-id="b1387-102">基本数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1387-102">Elementary Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b1387-103">提供了一组预定义的数据类型，您可以使用很多编程元素。</span><span class="sxs-lookup"><span data-stu-id="b1387-103"> supplies a set of predefined data types, which you can use for many of your programming elements.</span></span> <span data-ttu-id="b1387-104">本部分介绍这些类型以及如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="b1387-104">This section describes these types and how to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1387-105">在 Visual Basic 中的所有基本数据类型支持的结构或在一个类<xref:System>命名空间。</xref:System></span><span class="sxs-lookup"><span data-stu-id="b1387-105">Every elementary data type in Visual Basic is supported by a structure or a class that is in the <xref:System> namespace.</span></span> <span data-ttu-id="b1387-106">编译器使用每个数据类型关键字作为别名的基础结构或类。</span><span class="sxs-lookup"><span data-stu-id="b1387-106">The compiler uses each data type keyword as an alias for the underlying structure or class.</span></span> <span data-ttu-id="b1387-107">例如，通过使用保留的字声明一个变量`Byte`等同于使用完全限定的结构名称<xref:System.Byte?displayProperty=fullName>。</xref:System.Byte?displayProperty=fullName>声明</span><span class="sxs-lookup"><span data-stu-id="b1387-107">For example, declaring a variable by using the reserved word `Byte` is the same as declaring it by using the fully qualified structure name <xref:System.Byte?displayProperty=fullName>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1387-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="b1387-108">In This Section</span></span>  
 [<span data-ttu-id="b1387-109">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="b1387-109">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 <span data-ttu-id="b1387-110">描述整型和非整型数值类型。</span><span class="sxs-lookup"><span data-stu-id="b1387-110">Describes the integral and non-integral numeric types.</span></span>  
  
 [<span data-ttu-id="b1387-111">字符数据类型</span><span class="sxs-lookup"><span data-stu-id="b1387-111">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 <span data-ttu-id="b1387-112">描述`Char`和`String`类型。</span><span class="sxs-lookup"><span data-stu-id="b1387-112">Describes the `Char` and `String` types.</span></span>  
  
 [<span data-ttu-id="b1387-113">杂项数据类型</span><span class="sxs-lookup"><span data-stu-id="b1387-113">Miscellaneous Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 <span data-ttu-id="b1387-114">描述`Boolean`， `Date`，和`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="b1387-114">Describes the `Boolean`, `Date`, and `Object` types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b1387-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="b1387-115">Related Sections</span></span>  
 [<span data-ttu-id="b1387-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="b1387-116">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="b1387-117">引入了[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型并说明如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="b1387-117">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="b1387-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="b1387-118">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="b1387-119">提供由提供的基本数据类型的概述[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b1387-119">Provides an overview of the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
