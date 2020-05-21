---
title: ICorThreadpool::CorChangeTimer 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: e2174afe0ee96bd153b7b40c73c0185d9058a0dc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760316"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="ccdb7-102">ICorThreadpool::CorChangeTimer 方法</span><span class="sxs-lookup"><span data-stu-id="ccdb7-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="ccdb7-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="ccdb7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ccdb7-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ccdb7-105">要求</span><span class="sxs-lookup"><span data-stu-id="ccdb7-105">Requirements</span></span>  
 <span data-ttu-id="ccdb7-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdb7-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdb7-107">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ccdb7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccdb7-108">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ccdb7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccdb7-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdb7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdb7-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccdb7-110">See also</span></span>

- [<span data-ttu-id="ccdb7-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="ccdb7-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
