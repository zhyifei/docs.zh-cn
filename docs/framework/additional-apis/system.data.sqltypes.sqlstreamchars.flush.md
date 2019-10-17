---
title: SqlStreamChars 方法（SqlTypes）
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
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395614"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="0fc0a-102">SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="0fc0a-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="0fc0a-103">当在派生类中重写时，将清除该流的所有缓冲区，并使得所有缓冲数据被写入到基础设备。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="0fc0a-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0fc0a-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0fc0a-106">对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fc0a-107">语法</span><span class="sxs-lookup"><span data-stu-id="0fc0a-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="0fc0a-108">备注</span><span class="sxs-lookup"><span data-stu-id="0fc0a-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0fc0a-109">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0fc0a-110">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0fc0a-111">要求</span><span class="sxs-lookup"><span data-stu-id="0fc0a-111">Requirements</span></span>

<span data-ttu-id="0fc0a-112">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0fc0a-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0fc0a-113">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="0fc0a-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0fc0a-114">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="0fc0a-114">**.NET Framework versions:** Available since 2.0.</span></span>
