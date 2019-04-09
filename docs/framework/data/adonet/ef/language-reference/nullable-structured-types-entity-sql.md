---
title: 可以为 null 的结构化类型 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127850"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="9b3bc-102">可以为 null 的结构化类型 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9b3bc-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="9b3bc-103">结构化类型的 `null` 实例是不存在的实例。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="9b3bc-104">这不同于其中所有属性都具有 `null` 值的现有实例。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="9b3bc-105">本主题介绍可以为 Null 的结构化类型，包括哪些类型可以为 null 以及哪些代码模式会产生可以为 Null 的结构化类型的 `null` 实例。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="9b3bc-106">可以为 Null 的结构化类型的种类</span><span class="sxs-lookup"><span data-stu-id="9b3bc-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="9b3bc-107">有三种可以为 Null 的结构化类型：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="9b3bc-108">行类型。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-108">Row types.</span></span>  
  
-   <span data-ttu-id="9b3bc-109">复杂类型。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-109">Complex types.</span></span>  
  
-   <span data-ttu-id="9b3bc-110">实体类型。</span><span class="sxs-lookup"><span data-stu-id="9b3bc-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="9b3bc-111">能够产生结构化类型的 null 实例的代码模式</span><span class="sxs-lookup"><span data-stu-id="9b3bc-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="9b3bc-112">以下方案会产生 `null` 实例：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="9b3bc-113">将 `null` 说明为结构化类型：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="9b3bc-114">将基类型向上转换为派生类型：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="9b3bc-115">对 false 条件进行外部联接：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9b3bc-116">--或</span><span class="sxs-lookup"><span data-stu-id="9b3bc-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="9b3bc-117">--或</span><span class="sxs-lookup"><span data-stu-id="9b3bc-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="9b3bc-118">取消 `null` 引用的引用：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="9b3bc-119">从空集合获取 ANYELEMENT：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="9b3bc-120">检查结构化类型实例是否为 `null`：</span><span class="sxs-lookup"><span data-stu-id="9b3bc-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b3bc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b3bc-121">See also</span></span>

- [<span data-ttu-id="9b3bc-122">Entity SQL 概述</span><span class="sxs-lookup"><span data-stu-id="9b3bc-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
