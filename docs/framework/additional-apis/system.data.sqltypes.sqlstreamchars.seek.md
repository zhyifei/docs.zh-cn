---
title: SqlStreamChars （Int64，SeekOrigin）方法（SqlTypes）
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: db8aba0a86c140ba62af8056011226532d415951
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395594"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="177f7-102">SqlStreamChars （Int64，SeekOrigin）方法</span><span class="sxs-lookup"><span data-stu-id="177f7-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="177f7-103">当在派生类中重写时，设置当前流中的位置。</span><span class="sxs-lookup"><span data-stu-id="177f7-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="177f7-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="177f7-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="177f7-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="177f7-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="177f7-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="177f7-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="177f7-107">参数</span><span class="sxs-lookup"><span data-stu-id="177f7-107">Parameters</span></span>

`offset`\
<span data-ttu-id="177f7-108">相对于 @no__t 0 的字节偏移量。</span><span class="sxs-lookup"><span data-stu-id="177f7-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="177f7-109">枚举值之一，指示要从中获取新位置的参考点。</span><span class="sxs-lookup"><span data-stu-id="177f7-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="177f7-110">返回</span><span class="sxs-lookup"><span data-stu-id="177f7-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="177f7-111">当前流中的新位置。</span><span class="sxs-lookup"><span data-stu-id="177f7-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="177f7-112">备注</span><span class="sxs-lookup"><span data-stu-id="177f7-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="177f7-113">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="177f7-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="177f7-114">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="177f7-114">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="177f7-115">要求</span><span class="sxs-lookup"><span data-stu-id="177f7-115">Requirements</span></span>

<span data-ttu-id="177f7-116">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="177f7-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="177f7-117">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="177f7-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="177f7-118">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="177f7-118">**.NET Framework versions:** Available since 2.0.</span></span>
