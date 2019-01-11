---
title: SqlStreamChars.SetLength(Int64) 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c7199cbd08e62b1f0391437a0c1864cb9036fe1f
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222686"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="ad945-102">SqlStreamChars.SetLength(Int64) 方法</span><span class="sxs-lookup"><span data-stu-id="ad945-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="ad945-103">当在派生类中重写时释放流使用的资源。</span><span class="sxs-lookup"><span data-stu-id="ad945-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="ad945-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="ad945-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="ad945-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="ad945-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="ad945-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="ad945-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="ad945-107">参数</span><span class="sxs-lookup"><span data-stu-id="ad945-107">Parameters</span></span>

`value`\
<span data-ttu-id="ad945-108">所需的当前流的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="ad945-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad945-109">备注</span><span class="sxs-lookup"><span data-stu-id="ad945-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ad945-110">`SqlStreamChars.SetLength`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="ad945-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ad945-111">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="ad945-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad945-112">要求</span><span class="sxs-lookup"><span data-stu-id="ad945-112">Requirements</span></span>

<span data-ttu-id="ad945-113">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="ad945-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="ad945-114">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="ad945-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="ad945-115">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="ad945-115">**.NET Framework versions:** Available since 2.0.</span></span>