---
title: SmiOrderProperty.Item 属性 (Microsoft.SqlServer.Server)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2d8788f610d80c30baf51bff0131f0834d59fcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634576"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="e7aa5-102">SmiOrderProperty.Item 属性</span><span class="sxs-lookup"><span data-stu-id="e7aa5-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="e7aa5-103">获取实体的列顺序。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-103">Gets the column order for the entity.</span></span> <span data-ttu-id="e7aa5-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e7aa5-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e7aa5-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7aa5-107">语法</span><span class="sxs-lookup"><span data-stu-id="e7aa5-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="e7aa5-108">属性值</span><span class="sxs-lookup"><span data-stu-id="e7aa5-108">Property value</span></span>

<span data-ttu-id="e7aa5-109">列的顺序。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7aa5-110">备注</span><span class="sxs-lookup"><span data-stu-id="e7aa5-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e7aa5-111">`SmiOrderProperty.Item`属性内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e7aa5-112">Microsoft 不支持在生产应用程序在任何情况下使用此属性。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e7aa5-113">要求</span><span class="sxs-lookup"><span data-stu-id="e7aa5-113">Requirements</span></span>

<span data-ttu-id="e7aa5-114">**Namespace**：<xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="e7aa5-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="e7aa5-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="e7aa5-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e7aa5-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="e7aa5-116">**.NET Framework versions:** Available since 2.0.</span></span>
