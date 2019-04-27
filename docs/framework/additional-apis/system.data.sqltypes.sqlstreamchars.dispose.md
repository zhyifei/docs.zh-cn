---
title: SqlStreamChars.Dispose(Boolean) 方法 (System.Data.SqlTypes)
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
ms.openlocfilehash: cc8df68a608000d89dd322b0d396504483bbf372
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675151"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="b1f8b-102">SqlStreamChars.Dispose(Boolean) 方法</span><span class="sxs-lookup"><span data-stu-id="b1f8b-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="b1f8b-103">当在派生类中重写时释放流使用的资源。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="b1f8b-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="b1f8b-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="b1f8b-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="b1f8b-107">参数</span><span class="sxs-lookup"><span data-stu-id="b1f8b-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="b1f8b-108">若要释放托管资源和非托管资源，则为 `true`；若仅释放非托管资源，则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1f8b-109">备注</span><span class="sxs-lookup"><span data-stu-id="b1f8b-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b1f8b-110">`SqlStreamChars.Dispose`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b1f8b-111">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1f8b-112">要求</span><span class="sxs-lookup"><span data-stu-id="b1f8b-112">Requirements</span></span>

<span data-ttu-id="b1f8b-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="b1f8b-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="b1f8b-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="b1f8b-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="b1f8b-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="b1f8b-115">**.NET Framework versions:** Available since 2.0.</span></span>