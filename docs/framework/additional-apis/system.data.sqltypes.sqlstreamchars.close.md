---
title: SqlStreamChars.Close 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5b7ba05b0659bfd2cad165826469c0c8f0674797
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221162"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="9399c-102">SqlStreamChars.Close 方法</span><span class="sxs-lookup"><span data-stu-id="9399c-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="9399c-103">关闭当前流并释放与该流关联的所有系统资源。</span><span class="sxs-lookup"><span data-stu-id="9399c-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="9399c-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="9399c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="9399c-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="9399c-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="9399c-106"> 对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="9399c-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="9399c-107">备注</span><span class="sxs-lookup"><span data-stu-id="9399c-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="9399c-108">`SqlStreamChars.Close`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="9399c-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9399c-109">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="9399c-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9399c-110">要求</span><span class="sxs-lookup"><span data-stu-id="9399c-110">Requirements</span></span>

<span data-ttu-id="9399c-111">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="9399c-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="9399c-112">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="9399c-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="9399c-113">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="9399c-113">**.NET Framework versions:** Available since 2.0.</span></span>