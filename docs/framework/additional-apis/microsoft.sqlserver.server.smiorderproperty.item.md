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
ms.openlocfilehash: 499522a11cac744c14ac32cf3bfe485a46b19d93
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634318"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="44c06-102">SmiOrderProperty.Item 属性</span><span class="sxs-lookup"><span data-stu-id="44c06-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="44c06-103">获取实体的列顺序。</span><span class="sxs-lookup"><span data-stu-id="44c06-103">Gets the column order for the entity.</span></span> <span data-ttu-id="44c06-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="44c06-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="44c06-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="44c06-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="44c06-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="44c06-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="44c06-107">语法</span><span class="sxs-lookup"><span data-stu-id="44c06-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="44c06-108">属性值</span><span class="sxs-lookup"><span data-stu-id="44c06-108">Property value</span></span>

<span data-ttu-id="44c06-109">列的顺序。</span><span class="sxs-lookup"><span data-stu-id="44c06-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="44c06-110">备注</span><span class="sxs-lookup"><span data-stu-id="44c06-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="44c06-111">`SmiOrderProperty.Item`属性内部使用并且不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="44c06-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="44c06-112">Microsoft 不支持在生产应用程序在任何情况下使用此属性。</span><span class="sxs-lookup"><span data-stu-id="44c06-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="44c06-113">要求</span><span class="sxs-lookup"><span data-stu-id="44c06-113">Requirements</span></span>

<span data-ttu-id="44c06-114">**Namespace**：<xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="44c06-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="44c06-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="44c06-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="44c06-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="44c06-116">**.NET Framework versions:** Available since 2.0.</span></span>