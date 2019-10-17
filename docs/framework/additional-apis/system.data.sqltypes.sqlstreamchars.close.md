---
title: SqlStreamChars 方法（SqlTypes）
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: c33c60842d181be7011528ca7550f3d09f291f43
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395634"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="67273-102">SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="67273-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="67273-103">关闭当前流并释放与该流关联的任何系统资源。</span><span class="sxs-lookup"><span data-stu-id="67273-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="67273-104">包含此方法的程序集与 SQLAccess 具有友元关系。</span><span class="sxs-lookup"><span data-stu-id="67273-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="67273-105">它旨在 SQL Server 使用。</span><span class="sxs-lookup"><span data-stu-id="67273-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="67273-106"> 对于其他数据库，请使用该数据库提供的托管机制。</span><span class="sxs-lookup"><span data-stu-id="67273-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="67273-107">备注</span><span class="sxs-lookup"><span data-stu-id="67273-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="67273-108">@No__t-0 方法是私有的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="67273-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="67273-109">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="67273-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="67273-110">要求</span><span class="sxs-lookup"><span data-stu-id="67273-110">Requirements</span></span>

<span data-ttu-id="67273-111">**命名空间：** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="67273-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="67273-112">**程序集：** System.object （在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="67273-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="67273-113">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="67273-113">**.NET Framework versions:** Available since 2.0.</span></span>
