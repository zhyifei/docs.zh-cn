---
title: "基本数据类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ae0bb07688cf1e9573d02826f186811cd7340c90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="basic-data-types"></a><span data-ttu-id="9d601-102">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="9d601-102">Basic Data Types</span></span>
<span data-ttu-id="9d601-103">因为 LINQ to SQL 查询转换为 Transact-SQL 后才在 Microsoft SQL Server 上执行。</span><span class="sxs-lookup"><span data-stu-id="9d601-103">Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server.</span></span> <span data-ttu-id="9d601-104">LINQ to SQL 支持针对基本数据类型的许多和 SQL Server 一样的内置功能。</span><span class="sxs-lookup"><span data-stu-id="9d601-104">LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.</span></span>  
  
## <a name="casting"></a><span data-ttu-id="9d601-105">强制转换</span><span class="sxs-lookup"><span data-stu-id="9d601-105">Casting</span></span>  
 <span data-ttu-id="9d601-106">支持从源 CLR 类型到目标 CLR 类型的隐式或显式强制转换，前提是在 SQL Server 中存在类似的有效转换。</span><span class="sxs-lookup"><span data-stu-id="9d601-106">Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server.</span></span> <span data-ttu-id="9d601-107">有关 CLR 强制转换的详细信息，请参阅[CType 函数](~/docs/visual-basic/language-reference/functions/ctype-function.md)([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) 和[作为](~/docs/csharp/language-reference/keywords/as.md)。</span><span class="sxs-lookup"><span data-stu-id="9d601-107">For more information about CLR casting, see [CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and [as](~/docs/csharp/language-reference/keywords/as.md).</span></span> <span data-ttu-id="9d601-108">转换后，强制转换会更改对 CLR 表达式执行的操作的行为，使之与自然映射到目标类型的其他 CLR 表达式的行为匹配。</span><span class="sxs-lookup"><span data-stu-id="9d601-108">After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type.</span></span> <span data-ttu-id="9d601-109">强制转换还可以在继承映射的上下文中进行。</span><span class="sxs-lookup"><span data-stu-id="9d601-109">Casts are also translatable in the context of inheritance mapping.</span></span> <span data-ttu-id="9d601-110">可以将对象强制转换成更具体的实体子类型，以便可以访问其特定于子类型的数据。</span><span class="sxs-lookup"><span data-stu-id="9d601-110">Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="9d601-111">相等运算符</span><span class="sxs-lookup"><span data-stu-id="9d601-111">Equality Operators</span></span>  
 <span data-ttu-id="9d601-112">LINQ to SQL 支持以下 LINQ to SQL 查询内部的基本数据类型上的相等运算符：</span><span class="sxs-lookup"><span data-stu-id="9d601-112">LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:</span></span>  
  
-   <span data-ttu-id="9d601-113">相等和不相等运算符：支持对数值 <xref:System.Boolean>、<xref:System.DateTime> 和 <xref:System.TimeSpan> 类型的相等和不相等运算符。</span><span class="sxs-lookup"><span data-stu-id="9d601-113">Equal and Inequality Operator: Equality and inequality operators are supported for numeric <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types.</span></span> <span data-ttu-id="9d601-114">有关详细信息[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]运算符`=`和`<>`，请参阅[比较运算符](~/docs/visual-basic/language-reference/operators/comparison-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="9d601-114">For more about [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] operators `=` and `<>`, see [Comparison Operators](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span></span> <span data-ttu-id="9d601-115">有关 C# 比较运算符的详细信息`==`和`!=`，请参阅[= = 运算符](~/docs/csharp/language-reference/operators/equality-comparison-operator.md)和[！ = 运算符](~/docs/csharp/language-reference/operators/not-equal-operator.md)分别</span><span class="sxs-lookup"><span data-stu-id="9d601-115">For more information about C# comparison operators `==` and `!=`, see [== Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) and [!= Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md), respectively</span></span>  
  
-   <span data-ttu-id="9d601-116">Is 运算符：在使用继承映射时，`IS` 运算符具有受支持的转换形式。</span><span class="sxs-lookup"><span data-stu-id="9d601-116">Is operator: The `IS` operator has a supported translation when inheritance mapping is being used.</span></span> <span data-ttu-id="9d601-117">可以使用该运算符，而不用通过直接测试鉴别器列来确定对象是否属于特定实体类型，该运算符会转换为对鉴别器列的检查。</span><span class="sxs-lookup"><span data-stu-id="9d601-117">It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column.</span></span> <span data-ttu-id="9d601-118">有关 Visual Basic 和 C# 是运算符的详细信息，请参阅[Is 运算符](~/docs/visual-basic/language-reference/operators/is-operator.md)和[是](~/docs/csharp/language-reference/keywords/is.md)。</span><span class="sxs-lookup"><span data-stu-id="9d601-118">For more information about the Visual Basic and C# Is operators, see [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) and [is](~/docs/csharp/language-reference/keywords/is.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d601-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d601-119">See Also</span></span>  
 [<span data-ttu-id="9d601-120">SQL-CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="9d601-120">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="9d601-121">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="9d601-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
