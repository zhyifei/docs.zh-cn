---
title: FUNCTION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a195656d02d3b7e26ad4f0d8715fc8bf5663750b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="function-entity-sql"></a><span data-ttu-id="23dfb-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="23dfb-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="23dfb-103">在 Entity SQL 查询命令的范围内定义函数。</span><span class="sxs-lookup"><span data-stu-id="23dfb-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23dfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="23dfb-104">Syntax</span></span>  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a><span data-ttu-id="23dfb-105">自变量</span><span class="sxs-lookup"><span data-stu-id="23dfb-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="23dfb-106">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="23dfb-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="23dfb-107">函数中参数的名称。</span><span class="sxs-lookup"><span data-stu-id="23dfb-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="23dfb-108">属于函数的有效 Entity SQL 表达式。</span><span class="sxs-lookup"><span data-stu-id="23dfb-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="23dfb-109">函数中的命令，可以作用于传递给函数的 `parameter_name` 参数。</span><span class="sxs-lookup"><span data-stu-id="23dfb-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="23dfb-110">受支持类型的名称。</span><span class="sxs-lookup"><span data-stu-id="23dfb-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="23dfb-111">COLLECTION ( <type_definition`>` )</span><span class="sxs-lookup"><span data-stu-id="23dfb-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="23dfb-112">一个表达式，返回受支持类型、行或引用的集合。</span><span class="sxs-lookup"><span data-stu-id="23dfb-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="23dfb-113">REF **(**`data_type`**)**</span><span class="sxs-lookup"><span data-stu-id="23dfb-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="23dfb-114">一个表达式，返回对实体类型的引用。</span><span class="sxs-lookup"><span data-stu-id="23dfb-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="23dfb-115">ROW **(**`row_expression`**)**</span><span class="sxs-lookup"><span data-stu-id="23dfb-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="23dfb-116">一个表达式，从一个或多个值返回结构上类型化的匿名记录。</span><span class="sxs-lookup"><span data-stu-id="23dfb-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="23dfb-117">有关更多信息，请参见 [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="23dfb-117">For more information, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23dfb-118">备注</span><span class="sxs-lookup"><span data-stu-id="23dfb-118">Remarks</span></span>  
 <span data-ttu-id="23dfb-119">可以内联声明具有相同名称的多个函数，只要这些函数的签名不同即可。</span><span class="sxs-lookup"><span data-stu-id="23dfb-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="23dfb-120">有关详细信息，请参阅 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="23dfb-120">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="23dfb-121">只有在 Entity SQL 命令中定义了内联函数后，才可以在该命令中调用内联函数。</span><span class="sxs-lookup"><span data-stu-id="23dfb-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="23dfb-122">但是，在定义被调函数之前或之后，都可以在一个内联函数中调用另一个内联函数。</span><span class="sxs-lookup"><span data-stu-id="23dfb-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="23dfb-123">在下面的示例中，函数 A 在定义函数 B 之前调用函数 B：</span><span class="sxs-lookup"><span data-stu-id="23dfb-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="23dfb-124">有关详细信息，请参阅 [如何：调用用户定义的函数](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)。</span><span class="sxs-lookup"><span data-stu-id="23dfb-124">For more information, see [How to: Call a User-Defined Function](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02).</span></span>  
  
 <span data-ttu-id="23dfb-125">还可以在模型本身中声明函数。</span><span class="sxs-lookup"><span data-stu-id="23dfb-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="23dfb-126">在模型中声明的函数的执行方式与在命令中内联声明的函数的执行方式相同。</span><span class="sxs-lookup"><span data-stu-id="23dfb-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="23dfb-127">有关详细信息，请参阅[用户定义函数](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="23dfb-127">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23dfb-128">示例</span><span class="sxs-lookup"><span data-stu-id="23dfb-128">Example</span></span>  
 <span data-ttu-id="23dfb-129">下面的 Entity SQL 命令定义一个函数 `Products` ，该函数采用整数值来筛选返回的产品。</span><span class="sxs-lookup"><span data-stu-id="23dfb-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a><span data-ttu-id="23dfb-130">示例</span><span class="sxs-lookup"><span data-stu-id="23dfb-130">Example</span></span>  
 <span data-ttu-id="23dfb-131">下面的 Entity SQL 命令定义一个函数 `StringReturnsCollection` ，该函数采用字符串集合来筛选返回的联系人。</span><span class="sxs-lookup"><span data-stu-id="23dfb-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="23dfb-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="23dfb-132">See Also</span></span>  
 [<span data-ttu-id="23dfb-133">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="23dfb-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="23dfb-134">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="23dfb-134">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
