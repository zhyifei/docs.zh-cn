---
title: ICorDebugMDA::GetOSThreadId 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: e9846234f8217b822860c2400a54a91a651a0a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129816"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="40a72-102">ICorDebugMDA::GetOSThreadId 方法</span><span class="sxs-lookup"><span data-stu-id="40a72-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="40a72-103">获取操作系统（OS）线程标识符， [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)表示的托管调试助手（MDA）正在执行。</span><span class="sxs-lookup"><span data-stu-id="40a72-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a72-104">语法</span><span class="sxs-lookup"><span data-stu-id="40a72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40a72-105">参数</span><span class="sxs-lookup"><span data-stu-id="40a72-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="40a72-106">弄指向 OS 线程标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="40a72-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40a72-107">备注</span><span class="sxs-lookup"><span data-stu-id="40a72-107">Remarks</span></span>  
 <span data-ttu-id="40a72-108">使用 OS 线程而不是 ICorDebugThread 来实现以下情况：在本机线程上或在尚未输入托管代码的托管线程上触发 MDA。</span><span class="sxs-lookup"><span data-stu-id="40a72-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a72-109">要求</span><span class="sxs-lookup"><span data-stu-id="40a72-109">Requirements</span></span>  
 <span data-ttu-id="40a72-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40a72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40a72-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40a72-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40a72-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40a72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40a72-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a72-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="40a72-114">See also</span></span>

- [<span data-ttu-id="40a72-115">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="40a72-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="40a72-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="40a72-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
