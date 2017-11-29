---
title: "。 （成员访问）(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c9d5d8f2c90273b316379d3c2803835bab3faef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="aba93-103">.</span><span class="sxs-lookup"><span data-stu-id="aba93-103">.</span></span> <span data-ttu-id="aba93-104">（成员访问）(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="aba93-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="aba93-105">点运算符 （.） 是[!INCLUDE[esql](../../../../../../includes/esql-md.md)]成员访问运算符。</span><span class="sxs-lookup"><span data-stu-id="aba93-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="aba93-106">使用成员访问运算符可生成结构化概念模型类型实例的属性或字段的值。</span><span class="sxs-lookup"><span data-stu-id="aba93-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba93-107">语法</span><span class="sxs-lookup"><span data-stu-id="aba93-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="aba93-108">参数</span><span class="sxs-lookup"><span data-stu-id="aba93-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="aba93-109">结构化概念模型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="aba93-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="aba93-110">属于对象实例的属性或字段。</span><span class="sxs-lookup"><span data-stu-id="aba93-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aba93-111">备注</span><span class="sxs-lookup"><span data-stu-id="aba93-111">Remarks</span></span>  
 <span data-ttu-id="aba93-112">点 (.) 运算符可以用于从记录中提取字段，类似于提取复杂类型或实体类型的属性。</span><span class="sxs-lookup"><span data-stu-id="aba93-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="aba93-113">例如，如果类型 Name 的 n 是类型 Person 的成员，而 p 是类型 Person 的实例，则 p.n 是合法的成员访问表达式，该表达式生成类型为 Name 的值。</span><span class="sxs-lookup"><span data-stu-id="aba93-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="aba93-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aba93-114">See Also</span></span>  
 [<span data-ttu-id="aba93-115">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="aba93-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
