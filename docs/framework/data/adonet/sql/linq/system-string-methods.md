---
title: "System.String 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cfddba1bfa7bf7cefba917be0026b1c366f3513
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="systemstring-methods"></a><span data-ttu-id="5ad3d-102">System.String 方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="5ad3d-103"> 不支持以下 <xref:System.String> 方法。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-103"> does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="5ad3d-104">一般情况下不支持的 System.String 方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="5ad3d-105">一般情况下不支持的 <xref:System.String> 方法：</span><span class="sxs-lookup"><span data-stu-id="5ad3d-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
-   <span data-ttu-id="5ad3d-106">区分区域性的重载 (采用方法`CultureInfo`  /  `StringComparison`  /  `IFormatProvider`)。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
-   <span data-ttu-id="5ad3d-107">带有或生成 `char` 数组的方法。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="5ad3d-108">不支持的 System.String 静态方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="5ad3d-109">不支持的 System.String 静态方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="5ad3d-110">不支持的 System.String 非静态方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="5ad3d-111">不支持的 System.String 非静态方法</span><span class="sxs-lookup"><span data-stu-id="5ad3d-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="5ad3d-112">与 .NET 的差异</span><span class="sxs-lookup"><span data-stu-id="5ad3d-112">Differences from .NET</span></span>  
  
-   <span data-ttu-id="5ad3d-113">查询不考虑可能在服务器上生效的 SQL Server 排序规则，因而默认情况下将提供区分区域性和大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="5ad3d-114">此行为不同于 .NET Framework 默认的区分大小写的语义。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="5ad3d-115">当`LastIndexOf`返回 0 的字符串是`NULL`或找到的位置为 0。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
-   <span data-ttu-id="5ad3d-116">对长度固定的字符串（`CHAR`、`NCHAR`）执行串联或其他运算时，可能会返回意外结果，原因是这些类型会自动在数据库中应用空白。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
-   <span data-ttu-id="5ad3d-117">由于许多方法（如 `Replace`、`ToLower`、`ToUpper`）和字符索引器未实现对 `TEXT` 或 `NTEXT` 列以及 XML 的有效转换，因此，如果对它们进行正常转换，则会发生 `SqlExceptions`。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="5ad3d-118">对这些类型而言，这种行为被视为可接受。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="5ad3d-119">但是，所有字符串运算都必须符合 `VARCHAR`、`NVARCHAR`、`VARCHAR(max)` 和 `NVARCHAR(max)` 的公共语言运行库 (CLR) 语义。</span><span class="sxs-lookup"><span data-stu-id="5ad3d-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad3d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ad3d-120">See Also</span></span>  
 [<span data-ttu-id="5ad3d-121">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="5ad3d-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
