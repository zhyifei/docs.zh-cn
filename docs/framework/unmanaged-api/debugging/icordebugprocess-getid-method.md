---
title: ICorDebugProcess::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
ms.openlocfilehash: ae0c23e3d48df6add8951a6d90029185a99bb323
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128832"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="760f8-102">ICorDebugProcess::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="760f8-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="760f8-103">获取进程的操作系统（OS） ID。</span><span class="sxs-lookup"><span data-stu-id="760f8-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="760f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="760f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="760f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="760f8-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="760f8-106">弄进程的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="760f8-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="760f8-107">要求</span><span class="sxs-lookup"><span data-stu-id="760f8-107">Requirements</span></span>  
 <span data-ttu-id="760f8-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="760f8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="760f8-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="760f8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="760f8-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="760f8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="760f8-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="760f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
