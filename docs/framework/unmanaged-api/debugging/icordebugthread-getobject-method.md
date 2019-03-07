---
title: ICorDebugThread::GetObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd5a7696e7630b21c8bdfa7e4d2f902d6f36995
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490250"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="5183e-102">ICorDebugThread::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="5183e-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="5183e-103">获取公共语言运行时 (CLR) 线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="5183e-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5183e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5183e-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5183e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5183e-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="5183e-106">[out]指向一个 ICorDebugValue 接口对象，表示 CLR 线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5183e-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5183e-107">要求</span><span class="sxs-lookup"><span data-stu-id="5183e-107">Requirements</span></span>  
 <span data-ttu-id="5183e-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5183e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5183e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5183e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5183e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5183e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5183e-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5183e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5183e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5183e-112">See also</span></span>
- <xref:System.Threading.Thread>
