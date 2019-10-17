---
title: SqlStreamChars （布尔值）方法（SqlTypes）
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 44dc97835b8a7141064e8de4d2d5325c40be5a34
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395768"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="3439f-102">SqlStreamChars （布尔值）方法</span><span class="sxs-lookup"><span data-stu-id="3439f-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="3439f-103">当在派生类中重写时，释放流使用的资源。</span><span class="sxs-lookup"><span data-stu-id="3439f-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="3439f-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="3439f-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3439f-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="3439f-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="3439f-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="3439f-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="3439f-107">参数</span><span class="sxs-lookup"><span data-stu-id="3439f-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="3439f-108">若要释放托管资源和非托管资源，则为 `true`；若仅释放非托管资源，则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3439f-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="3439f-109">备注</span><span class="sxs-lookup"><span data-stu-id="3439f-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3439f-110">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="3439f-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3439f-111">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="3439f-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3439f-112">要求</span><span class="sxs-lookup"><span data-stu-id="3439f-112">Requirements</span></span>

<span data-ttu-id="3439f-113">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3439f-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3439f-114">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="3439f-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3439f-115">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="3439f-115">**.NET Framework versions:** Available since 2.0.</span></span>
