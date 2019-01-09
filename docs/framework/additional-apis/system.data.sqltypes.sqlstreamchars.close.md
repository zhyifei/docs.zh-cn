---
title: SqlStreamChars.Close 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 893ee729b864d381c4e4686024687f309d15d214
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152650"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="3cc8f-102">SqlStreamChars.Close 方法</span><span class="sxs-lookup"><span data-stu-id="3cc8f-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="3cc8f-103">关闭当前流并释放与该流关联的所有系统资源。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="3cc8f-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3cc8f-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="3cc8f-106"> 对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="3cc8f-107">备注</span><span class="sxs-lookup"><span data-stu-id="3cc8f-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3cc8f-108">`SqlStreamChars.Close`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3cc8f-109">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3cc8f-110">要求</span><span class="sxs-lookup"><span data-stu-id="3cc8f-110">Requirements</span></span>

<span data-ttu-id="3cc8f-111">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3cc8f-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3cc8f-112">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="3cc8f-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3cc8f-113">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="3cc8f-113">**.NET Framework versions:** Available since 2.0.</span></span>