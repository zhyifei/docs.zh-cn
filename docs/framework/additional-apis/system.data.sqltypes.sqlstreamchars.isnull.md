---
title: SqlStreamChars.IsNull 属性 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7bef26119e31658b8495df402bbc07341cd84cf7
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222553"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="936ce-102">SqlStreamChars.IsNull 属性</span><span class="sxs-lookup"><span data-stu-id="936ce-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="936ce-103">当在派生类中重写时获取一个值，指示流是否`null`。</span><span class="sxs-lookup"><span data-stu-id="936ce-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="936ce-104">包含此属性的程序集具有与 SQLAccess.dll 友元关系。</span><span class="sxs-lookup"><span data-stu-id="936ce-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="936ce-105">它被用于 SQL server 上。</span><span class="sxs-lookup"><span data-stu-id="936ce-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="936ce-106">对于其他数据库，使用提供该数据库的宿主机制。</span><span class="sxs-lookup"><span data-stu-id="936ce-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="936ce-107">语法</span><span class="sxs-lookup"><span data-stu-id="936ce-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="936ce-108">属性值</span><span class="sxs-lookup"><span data-stu-id="936ce-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="936ce-109">`true` 如果流已`null`; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="936ce-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="936ce-110">备注</span><span class="sxs-lookup"><span data-stu-id="936ce-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="936ce-111">`SqlStreamChars.IsNull`属性是私有的不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="936ce-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="936ce-112">Microsoft 不支持在生产应用程序在任何情况下使用此字段。</span><span class="sxs-lookup"><span data-stu-id="936ce-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="936ce-113">要求</span><span class="sxs-lookup"><span data-stu-id="936ce-113">Requirements</span></span>

<span data-ttu-id="936ce-114">**Namespace**：<xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="936ce-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="936ce-115">**程序集：** System.Data （在 System.Data.dll 中)</span><span class="sxs-lookup"><span data-stu-id="936ce-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="936ce-116">**.NET framework 版本：** 自 2.0 之后可用。</span><span class="sxs-lookup"><span data-stu-id="936ce-116">**.NET Framework versions:** Available since 2.0.</span></span>