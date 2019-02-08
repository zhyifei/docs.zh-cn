---
title: SqlStreamChars.Dispose(Boolean) 方法 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4e6cfd6d4c04b1a2835b6e34b82c95b564dea588
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826858"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="5e247-102">SqlStreamChars.Dispose(Boolean) 方法</span><span class="sxs-lookup"><span data-stu-id="5e247-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="5e247-103">当在派生类中重写时释放流使用的资源。</span><span class="sxs-lookup"><span data-stu-id="5e247-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="5e247-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="5e247-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5e247-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="5e247-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5e247-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="5e247-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="5e247-107">参数</span><span class="sxs-lookup"><span data-stu-id="5e247-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="5e247-108">若要释放托管资源和非托管资源，则为 `true`；若仅释放非托管资源，则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5e247-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e247-109">备注</span><span class="sxs-lookup"><span data-stu-id="5e247-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5e247-110">`SqlStreamChars.Dispose`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="5e247-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5e247-111">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="5e247-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e247-112">要求</span><span class="sxs-lookup"><span data-stu-id="5e247-112">Requirements</span></span>

<span data-ttu-id="5e247-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5e247-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5e247-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="5e247-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5e247-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="5e247-115">**.NET Framework versions:** Available since 2.0.</span></span>