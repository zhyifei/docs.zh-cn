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
ms.openlocfilehash: 95b7a2f6d35104c3353853549dacc783355feb5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805337"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="1d96f-102">IDebuggerInfo::IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="1d96f-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="1d96f-103">获取一个值，该值指示托管调试器是否已附加到此进程。</span><span class="sxs-lookup"><span data-stu-id="1d96f-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d96f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d96f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d96f-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d96f-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="1d96f-106">弄一个指向值的指针， `true` 如果托管调试器附加到进程，则该值为; 否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1d96f-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d96f-107">要求</span><span class="sxs-lookup"><span data-stu-id="1d96f-107">Requirements</span></span>  
 <span data-ttu-id="1d96f-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d96f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d96f-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1d96f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d96f-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1d96f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d96f-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d96f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d96f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d96f-112">See also</span></span>

- [<span data-ttu-id="1d96f-113">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1d96f-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
