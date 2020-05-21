---
title: ICorThreadpool::CorCreateTimer 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: bd48b9167a803da6e27c8d8ebc3a2b13508ff5c9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760315"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="0a88a-102">ICorThreadpool::CorCreateTimer 方法</span><span class="sxs-lookup"><span data-stu-id="0a88a-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="0a88a-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="0a88a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a88a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a88a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0a88a-105">要求</span><span class="sxs-lookup"><span data-stu-id="0a88a-105">Requirements</span></span>  
 <span data-ttu-id="0a88a-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a88a-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a88a-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0a88a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a88a-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0a88a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a88a-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a88a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a88a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a88a-110">See also</span></span>

- [<span data-ttu-id="0a88a-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="0a88a-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
