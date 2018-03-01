---
title: "ICorDebugThread::GetObject 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c7802b51a8012b46b1d0bd9de5fbe9d3c6ff0da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="f38a5-102">ICorDebugThread::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="f38a5-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="f38a5-103">获取公共语言运行时 (CLR) 线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f38a5-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f38a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f38a5-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f38a5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f38a5-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="f38a5-106">[out]指向表示 CLR 线程 ICorDebugValue 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f38a5-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f38a5-107">惠?</span><span class="sxs-lookup"><span data-stu-id="f38a5-107">Requirements</span></span>  
 <span data-ttu-id="f38a5-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f38a5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f38a5-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f38a5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f38a5-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f38a5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f38a5-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f38a5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38a5-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f38a5-112">See Also</span></span>  
 <xref:System.Threading.Thread>
