---
title: ICorDebugModule::EnableJITDebugging 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109723"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="52913-102">ICorDebugModule::EnableJITDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="52913-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="52913-103">控制实时（JIT）编译器是否保留此模块内的方法的调试信息。</span><span class="sxs-lookup"><span data-stu-id="52913-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52913-104">语法</span><span class="sxs-lookup"><span data-stu-id="52913-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52913-105">参数</span><span class="sxs-lookup"><span data-stu-id="52913-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="52913-106">中将此值设置为 "`true`"，以使 JIT 编译器能够在此模块中的每个方法的 Microsoft 中间语言（MSIL）版本和 JIT 编译版本之间保留映射信息。</span><span class="sxs-lookup"><span data-stu-id="52913-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="52913-107">中将此值设置为 "`true`"，以允许 JIT 编译器生成具有特定于调试的特定于 JIT 的优化的代码。</span><span class="sxs-lookup"><span data-stu-id="52913-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52913-108">备注</span><span class="sxs-lookup"><span data-stu-id="52913-108">Remarks</span></span>  
 <span data-ttu-id="52913-109">默认情况下，调试程序处于活动状态时加载的所有模块都已启用 JIT 调试。</span><span class="sxs-lookup"><span data-stu-id="52913-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="52913-110">以编程方式启用或禁用设置将覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="52913-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52913-111">要求</span><span class="sxs-lookup"><span data-stu-id="52913-111">Requirements</span></span>  
 <span data-ttu-id="52913-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52913-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52913-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52913-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52913-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52913-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52913-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52913-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
