---
title: ICorDebugAssembly::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: 49b234b065eb66dc2ec0bc7e991117c5b54a92f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196351"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="a9565-102">ICorDebugAssembly::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a9565-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="a9565-103">获取一个接口指针，该指针指向运行此 ICorDebugAssembly 实例的进程。</span><span class="sxs-lookup"><span data-stu-id="a9565-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9565-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9565-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9565-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9565-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="a9565-106">弄指向表示进程的 ICorDebugProcess 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a9565-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9565-107">要求</span><span class="sxs-lookup"><span data-stu-id="a9565-107">Requirements</span></span>  
 <span data-ttu-id="a9565-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9565-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9565-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9565-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9565-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9565-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9565-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9565-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
