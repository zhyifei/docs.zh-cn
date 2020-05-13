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
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212992"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="4bd0f-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="4bd0f-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="4bd0f-103">获取当前编译器标志设置，公共语言运行时（CLR）使用这些设置来选择要加载到此进程中的正确预编译（即本机）映像。</span><span class="sxs-lookup"><span data-stu-id="4bd0f-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bd0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd0f-105">参数</span><span class="sxs-lookup"><span data-stu-id="4bd0f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="4bd0f-106">弄指向[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)枚举值的按位组合的指针，这些值用于选择要加载的正确预编译映像。</span><span class="sxs-lookup"><span data-stu-id="4bd0f-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bd0f-107">备注</span><span class="sxs-lookup"><span data-stu-id="4bd0f-107">Remarks</span></span>  
 <span data-ttu-id="4bd0f-108">使用[ICorDebugProcess2：： SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md)方法设置 CLR 将用于选择要加载的正确预编译图像的标志。</span><span class="sxs-lookup"><span data-stu-id="4bd0f-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd0f-109">要求</span><span class="sxs-lookup"><span data-stu-id="4bd0f-109">Requirements</span></span>  
 <span data-ttu-id="4bd0f-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd0f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd0f-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bd0f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bd0f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd0f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd0f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
