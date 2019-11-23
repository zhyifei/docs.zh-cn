---
title: SqlStreamChars. CanSeek 属性（SqlTypes）
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395781"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="2f47c-102">SqlStreamChars. CanSeek 属性</span><span class="sxs-lookup"><span data-stu-id="2f47c-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="2f47c-103">当在派生类中重写时，获取一个值，该值指示当前流是否支持查找操作。</span><span class="sxs-lookup"><span data-stu-id="2f47c-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="2f47c-104">包含此属性的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="2f47c-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2f47c-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="2f47c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2f47c-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="2f47c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="2f47c-107">属性值</span><span class="sxs-lookup"><span data-stu-id="2f47c-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="2f47c-108">`true` 如果当前流支持查找操作，则为; 否则为。否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="2f47c-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f47c-109">备注</span><span class="sxs-lookup"><span data-stu-id="2f47c-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2f47c-110">`SqlStreamChars.CanSeek` 属性是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="2f47c-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2f47c-111">在任何情况下，Microsoft 不支持在生产应用程序中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="2f47c-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f47c-112">要求</span><span class="sxs-lookup"><span data-stu-id="2f47c-112">Requirements</span></span>

<span data-ttu-id="2f47c-113">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2f47c-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2f47c-114">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="2f47c-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2f47c-115">**.NET framework 版本**：自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="2f47c-115">**.NET Framework versions:** Available since 2.0.</span></span>
