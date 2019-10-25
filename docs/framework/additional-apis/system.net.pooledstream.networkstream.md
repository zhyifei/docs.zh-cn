---
title: PooledStream. NetworkStream 属性（System.Net）
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847228"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="36212-102">PooledStream. NetworkStream 属性</span><span class="sxs-lookup"><span data-stu-id="36212-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="36212-103">获取或设置 `PooledStream` 套接字的网络流。</span><span class="sxs-lookup"><span data-stu-id="36212-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="36212-104">语法</span><span class="sxs-lookup"><span data-stu-id="36212-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="36212-105">属性值</span><span class="sxs-lookup"><span data-stu-id="36212-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="36212-106">`PooledStream` 套接字的网络流。</span><span class="sxs-lookup"><span data-stu-id="36212-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="36212-107">备注</span><span class="sxs-lookup"><span data-stu-id="36212-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="36212-108">`PooledStream.NetworkStream` 属性是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="36212-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="36212-109">在任何情况下，Microsoft 不支持在生产应用程序中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="36212-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="36212-110">要求</span><span class="sxs-lookup"><span data-stu-id="36212-110">Requirements</span></span>

<span data-ttu-id="36212-111">**命名空间：** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="36212-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="36212-112">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="36212-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="36212-113">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="36212-113">**.NET Framework versions:** Available since 2.0.</span></span>
