---
title: IDebuggerInfo::IsDebuggerAttached 方法
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
ms.openlocfilehash: cbd6fa5f7935a57799d695c3ebb617d856e6dbd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133181"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="b947b-102">IDebuggerInfo::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="b947b-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="b947b-103">获取一个值，该值指示托管调试器是否已附加到此进程。</span><span class="sxs-lookup"><span data-stu-id="b947b-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b947b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b947b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b947b-105">参数</span><span class="sxs-lookup"><span data-stu-id="b947b-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b947b-106">弄指向一个值的指针，如果将托管调试器附加到进程，则该值为 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="b947b-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b947b-107">要求</span><span class="sxs-lookup"><span data-stu-id="b947b-107">Requirements</span></span>  
 <span data-ttu-id="b947b-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b947b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b947b-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b947b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b947b-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b947b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b947b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b947b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b947b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b947b-112">See also</span></span>

- [<span data-ttu-id="b947b-113">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b947b-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
