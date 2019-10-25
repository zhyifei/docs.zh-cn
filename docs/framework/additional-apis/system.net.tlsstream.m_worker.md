---
title: TlsStream. m_Worker 字段（System.Net）
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.TlsStream.m_Worker
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: d335820d13e1e15e054e824a284615cdbf6c2094
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847240"
---
# <a name="tlsstreamm_worker-field"></a><span data-ttu-id="4b78b-102">TlsStream. m_Worker 字段</span><span class="sxs-lookup"><span data-stu-id="4b78b-102">TlsStream.m_Worker Field</span></span>

<span data-ttu-id="4b78b-103">表示 SSL 流的状态。</span><span class="sxs-lookup"><span data-stu-id="4b78b-103">Represents the state of the SSL stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b78b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b78b-104">Syntax</span></span>

```csharp
private SslState m_Worker;
```

## <a name="field-value"></a><span data-ttu-id="4b78b-105">字段值</span><span class="sxs-lookup"><span data-stu-id="4b78b-105">Field value</span></span>

`System.Net.Security.SslState`  
<span data-ttu-id="4b78b-106">SSL 流的状态。</span><span class="sxs-lookup"><span data-stu-id="4b78b-106">The state of the SSL stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b78b-107">备注</span><span class="sxs-lookup"><span data-stu-id="4b78b-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4b78b-108">`TlsStream.m_Worker` 字段是专用的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="4b78b-108">The `TlsStream.m_Worker` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4b78b-109">在任何情况下，Microsoft 不支持在生产应用程序中使用此字段。</span><span class="sxs-lookup"><span data-stu-id="4b78b-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b78b-110">要求</span><span class="sxs-lookup"><span data-stu-id="4b78b-110">Requirements</span></span>

<span data-ttu-id="4b78b-111">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4b78b-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4b78b-112">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="4b78b-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4b78b-113">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="4b78b-113">**.NET Framework versions:** Available since 2.0.</span></span>
