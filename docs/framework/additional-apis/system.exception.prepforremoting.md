---
title: PrepForRemoting 方法（系统）
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214887"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="bdcaa-102">Exception.PrepForRemoting 方法</span><span class="sxs-lookup"><span data-stu-id="bdcaa-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="bdcaa-103">保留服务器端堆栈跟踪，方法是将其追加到消息，然后在客户端调用站点重新引发异常。</span><span class="sxs-lookup"><span data-stu-id="bdcaa-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="bdcaa-104">返回</span><span class="sxs-lookup"><span data-stu-id="bdcaa-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="bdcaa-105">此 <xref:System.Exception> 实例。</span><span class="sxs-lookup"><span data-stu-id="bdcaa-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdcaa-106">备注</span><span class="sxs-lookup"><span data-stu-id="bdcaa-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bdcaa-107">`Exception.PrepForRemoting` 方法是内部的，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="bdcaa-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bdcaa-108">在任何情况下，Microsoft 不支持在生产应用程序中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="bdcaa-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bdcaa-109">要求</span><span class="sxs-lookup"><span data-stu-id="bdcaa-109">Requirements</span></span>

<span data-ttu-id="bdcaa-110">**命名空间：** <xref:System></span><span class="sxs-lookup"><span data-stu-id="bdcaa-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="bdcaa-111">**Assembly：** mscorlib （在 mscorlib.dll 中）</span><span class="sxs-lookup"><span data-stu-id="bdcaa-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="bdcaa-112">**.NET Framework 版本：** 自1.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="bdcaa-112">**.NET Framework versions:** Available since 1.0.</span></span>
