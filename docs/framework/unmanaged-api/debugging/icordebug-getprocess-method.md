---
title: ICorDebug::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: 59afc8ae7d66e81e4dca3923f9c6f7ff3a3a6605
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895383"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="75e5a-102">ICorDebug::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="75e5a-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="75e5a-103">获取指向指定进程的 "ICorDebugProcess" 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="75e5a-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="75e5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="75e5a-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="75e5a-106">中进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="75e5a-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="75e5a-107">弄指向指定进程的`ICorDebugProcess`实例地址的指针。</span><span class="sxs-lookup"><span data-stu-id="75e5a-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e5a-108">要求</span><span class="sxs-lookup"><span data-stu-id="75e5a-108">Requirements</span></span>  
 <span data-ttu-id="75e5a-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75e5a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e5a-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75e5a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75e5a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e5a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e5a-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e5a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e5a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75e5a-113">See also</span></span>

- [<span data-ttu-id="75e5a-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="75e5a-114">ICorDebug Interface</span></span>](icordebug-interface.md)
