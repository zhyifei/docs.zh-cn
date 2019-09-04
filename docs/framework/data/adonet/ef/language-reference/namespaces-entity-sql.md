---
title: 命名空间 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 395ffb23859be27b4897dfc352f6e44d52286b26
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249994"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="e5dcc-102">命名空间 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e5dcc-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e5dcc-103">引入命名空间以避免全局标识符（如类型名称、实体集、函数等）出现名称冲突。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-103">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="e5dcc-104">中[!INCLUDE[esql](../../../../../../includes/esql-md.md)]的命名空间支持与 .NET Framework 中的命名空间支持类似。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e5dcc-105">提供两种形式的 USING 子句：限定命名空间（其中，提供较短的别名以表示命名空间）和非限定命名空间，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="e5dcc-105">provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="e5dcc-106">名称解析规则</span><span class="sxs-lookup"><span data-stu-id="e5dcc-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="e5dcc-107">如果无法在本地作用域中解析标识符， [!INCLUDE[esql](../../../../../../includes/esql-md.md)]则尝试在全局作用域（命名空间）中查找该名称。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e5dcc-108">首先尝试将标识符（前缀）与其中一个限定的命名空间匹配。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="e5dcc-109">如果匹配，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 尝试在指定的命名空间中解析标识符的其余部分。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="e5dcc-110">如果未找到匹配项，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="e5dcc-111">接下来，[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 尝试搜索所有非限定命名空间（在序言中指定）以查找该标识符。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="e5dcc-112">如果只能在一个命名空间中找到此标识符，则返回该位置。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="e5dcc-113">如果多个命名空间对于该标识符具有匹配项，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="e5dcc-114">如果对于此标识符无法确定任何命名空间，则 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 将名称传递到下一个外部范围（<xref:System.Data.Common.DbCommand> 或 <xref:System.Data.Common.DbConnection> 对象），如下例中所示：</span><span class="sxs-lookup"><span data-stu-id="e5dcc-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="e5dcc-115">.NET Framework 中的不同之处</span><span class="sxs-lookup"><span data-stu-id="e5dcc-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="e5dcc-116">在 .NET Framework 中，您可以使用部分限定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-116">In the .NET Framework, you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e5dcc-117">不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-117">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="e5dcc-118">ADO.NET 使用</span><span class="sxs-lookup"><span data-stu-id="e5dcc-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="e5dcc-119">查询是通过 ADO.NET <xref:System.Data.Common.DbCommand> 对象表示的。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="e5dcc-120">可以在 <xref:System.Data.Common.DbCommand> 对象之上构建 <xref:System.Data.Common.DbConnection> 对象。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="e5dcc-121">也可以将命名空间指定为 <xref:System.Data.Common.DbCommand> 和 <xref:System.Data.Common.DbConnection> 对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="e5dcc-122">如果 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 无法在查询自身中解析标识符，则将探测外部命名空间（基于类似规则）。</span><span class="sxs-lookup"><span data-stu-id="e5dcc-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5dcc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5dcc-123">See also</span></span>

- [<span data-ttu-id="e5dcc-124">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="e5dcc-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e5dcc-125">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="e5dcc-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
