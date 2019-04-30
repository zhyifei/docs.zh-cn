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
ms.openlocfilehash: 7fa90aff73d94baf2cbf7d01f41710cb2aa10213
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994001"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="4938f-102">ICorDebugThread::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="4938f-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="4938f-103">获取公共语言运行时 (CLR) 线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4938f-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4938f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4938f-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4938f-105">参数</span><span class="sxs-lookup"><span data-stu-id="4938f-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="4938f-106">[out]指向一个 ICorDebugValue 接口对象，表示 CLR 线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4938f-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4938f-107">要求</span><span class="sxs-lookup"><span data-stu-id="4938f-107">Requirements</span></span>  
 <span data-ttu-id="4938f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4938f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4938f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4938f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4938f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4938f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4938f-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4938f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4938f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4938f-112">See also</span></span>

- <xref:System.Threading.Thread>
