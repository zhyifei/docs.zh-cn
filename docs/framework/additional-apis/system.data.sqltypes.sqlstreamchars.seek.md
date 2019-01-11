---
title: SqlStreamChars.Seek （Int64，SeekOrigin） 方法 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1710c802324920e324b18ddea843f0a532fa0d17
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222982"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="d10aa-102">SqlStreamChars.Seek （Int64，SeekOrigin） 方法</span><span class="sxs-lookup"><span data-stu-id="d10aa-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="d10aa-103">当在派生类中重写时，设置当前流中的位置。</span><span class="sxs-lookup"><span data-stu-id="d10aa-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="d10aa-104">包含此方法的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="d10aa-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d10aa-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="d10aa-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="d10aa-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="d10aa-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="d10aa-107">参数</span><span class="sxs-lookup"><span data-stu-id="d10aa-107">Parameters</span></span>

`offset`\
<span data-ttu-id="d10aa-108">字节偏移量相对于`origin`。</span><span class="sxs-lookup"><span data-stu-id="d10aa-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="d10aa-109">一个枚举值，该值指示要从中获取新位置的参考点。</span><span class="sxs-lookup"><span data-stu-id="d10aa-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="d10aa-110">返回</span><span class="sxs-lookup"><span data-stu-id="d10aa-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="d10aa-111">当前流中的新位置。</span><span class="sxs-lookup"><span data-stu-id="d10aa-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="d10aa-112">备注</span><span class="sxs-lookup"><span data-stu-id="d10aa-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d10aa-113">`SqlStreamChars.Seek`方法是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="d10aa-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d10aa-114">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="d10aa-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d10aa-115">要求</span><span class="sxs-lookup"><span data-stu-id="d10aa-115">Requirements</span></span>

<span data-ttu-id="d10aa-116">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d10aa-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d10aa-117">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="d10aa-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d10aa-118">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="d10aa-118">**.NET Framework versions:** Available since 2.0.</span></span>