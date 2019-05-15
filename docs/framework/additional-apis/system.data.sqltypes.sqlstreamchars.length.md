---
title: SqlStreamChars.Length 属性 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8f318f593237dc555d546858152bb03546c8306b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634443"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="50183-102">SqlStreamChars.Length 属性</span><span class="sxs-lookup"><span data-stu-id="50183-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="50183-103">当在派生类中重写时获取当前流的长度。</span><span class="sxs-lookup"><span data-stu-id="50183-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="50183-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="50183-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="50183-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="50183-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="50183-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="50183-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="50183-107">语法</span><span class="sxs-lookup"><span data-stu-id="50183-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="50183-108">属性值</span><span class="sxs-lookup"><span data-stu-id="50183-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="50183-109">流的长度。</span><span class="sxs-lookup"><span data-stu-id="50183-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="50183-110">备注</span><span class="sxs-lookup"><span data-stu-id="50183-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="50183-111">`SqlStreamChars.Length`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="50183-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="50183-112">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="50183-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="50183-113">要求</span><span class="sxs-lookup"><span data-stu-id="50183-113">Requirements</span></span>

<span data-ttu-id="50183-114">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="50183-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="50183-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="50183-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="50183-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="50183-116">**.NET Framework versions:** Available since 2.0.</span></span>
