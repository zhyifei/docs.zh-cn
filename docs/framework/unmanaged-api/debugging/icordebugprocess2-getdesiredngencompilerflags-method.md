---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a59067f72005e87152680e4f990fc74e4acdaa9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948910"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="2a6f7-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="2a6f7-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="2a6f7-103">获取当前的编译器标志设置的公共语言运行时 (CLR) 使用来选择正确的预编译 (即，本机) 映像加载到此过程。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a6f7-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a6f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a6f7-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="2a6f7-106">[out]指向的按位组合[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)用于选择正确的预编译的映像要加载的枚举值。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a6f7-107">备注</span><span class="sxs-lookup"><span data-stu-id="2a6f7-107">Remarks</span></span>  
 <span data-ttu-id="2a6f7-108">使用[ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)方法设置将用于选择正确的预编译的映像加载 CLR 的标志。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6f7-109">要求</span><span class="sxs-lookup"><span data-stu-id="2a6f7-109">Requirements</span></span>  
 <span data-ttu-id="2a6f7-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a6f7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6f7-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a6f7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a6f7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a6f7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a6f7-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
