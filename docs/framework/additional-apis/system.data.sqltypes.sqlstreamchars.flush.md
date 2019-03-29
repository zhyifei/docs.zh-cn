---
title: SqlStreamChars.Flush 方法 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd24a5ca420552f283da61ecd4edcad02965403
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634188"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="43269-102">SqlStreamChars.Flush 方法</span><span class="sxs-lookup"><span data-stu-id="43269-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="43269-103">当在派生类中重写时，将清除该流的所有缓冲区，并使得所有缓冲数据被写入到基础设备。</span><span class="sxs-lookup"><span data-stu-id="43269-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="43269-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="43269-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="43269-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="43269-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="43269-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="43269-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="43269-107">语法</span><span class="sxs-lookup"><span data-stu-id="43269-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="43269-108">备注</span><span class="sxs-lookup"><span data-stu-id="43269-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="43269-109">`SqlStreamChars.Flush`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="43269-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="43269-110">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="43269-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="43269-111">要求</span><span class="sxs-lookup"><span data-stu-id="43269-111">Requirements</span></span>

<span data-ttu-id="43269-112">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="43269-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="43269-113">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="43269-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="43269-114">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="43269-114">**.NET Framework versions:** Available since 2.0.</span></span>