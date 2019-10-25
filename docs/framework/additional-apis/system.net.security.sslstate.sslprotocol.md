---
title: SslState. SslProtocol 属性（系统 .Net）
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847246"
---
# <a name="sslstatesslprotocol-property"></a><span data-ttu-id="ce9c0-102">SslState. SslProtocol 属性</span><span class="sxs-lookup"><span data-stu-id="ce9c0-102">SslState.SslProtocol Property</span></span>

<span data-ttu-id="ce9c0-103">获取 SSL 协议版本。</span><span class="sxs-lookup"><span data-stu-id="ce9c0-103">Gets the SSL protocol versions.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce9c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce9c0-104">Syntax</span></span>

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a><span data-ttu-id="ce9c0-105">属性值</span><span class="sxs-lookup"><span data-stu-id="ce9c0-105">Property value</span></span>

<xref:System.Security.Authentication.SslProtocols>  
<span data-ttu-id="ce9c0-106">枚举值的按位组合，这些枚举值指定 SSL 协议版本。</span><span class="sxs-lookup"><span data-stu-id="ce9c0-106">A bitwise combination of the enumeration values that specify the SSL protocol versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce9c0-107">备注</span><span class="sxs-lookup"><span data-stu-id="ce9c0-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ce9c0-108">`SslState.SslProtocol` 属性是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="ce9c0-108">The `SslState.SslProtocol` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ce9c0-109">在任何情况下，Microsoft 不支持在生产应用程序中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="ce9c0-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce9c0-110">要求</span><span class="sxs-lookup"><span data-stu-id="ce9c0-110">Requirements</span></span>

<span data-ttu-id="ce9c0-111">**命名空间：** <xref:System.Net.Security></span><span class="sxs-lookup"><span data-stu-id="ce9c0-111">**Namespace:** <xref:System.Net.Security></span></span>

<span data-ttu-id="ce9c0-112">**程序集：** 系统（在 System.web 中）</span><span class="sxs-lookup"><span data-stu-id="ce9c0-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="ce9c0-113">**.NET Framework 版本：** 自2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="ce9c0-113">**.NET Framework versions:** Available since 2.0.</span></span>
