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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71722293bfb80a7e57393916560f922d970ea2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415637"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="2b078-102">ICorDebugModule::EnableJITDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="2b078-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="2b078-103">控制是否在实时 (JIT) 编译器会保留为此模块中的方法的调试信息。</span><span class="sxs-lookup"><span data-stu-id="2b078-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b078-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b078-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b078-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b078-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="2b078-106">[in]将此值设置为`true`启用 JIT 编译器，若要保留的 Microsoft 中间语言 (MSIL) 版本与此模块中的每个方法的 JIT 编译版本之间的映射信息。</span><span class="sxs-lookup"><span data-stu-id="2b078-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="2b078-107">[in]将此值设置为`true`启用 JIT 编译器生成使用用于调试的某些特定于 JIT 优化代码。</span><span class="sxs-lookup"><span data-stu-id="2b078-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b078-108">备注</span><span class="sxs-lookup"><span data-stu-id="2b078-108">Remarks</span></span>  
 <span data-ttu-id="2b078-109">默认情况下，调试器处于活动状态时加载的所有模块的情况下，启用 JIT 调试。</span><span class="sxs-lookup"><span data-stu-id="2b078-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="2b078-110">以编程方式启用或禁用设置重写全局设置。</span><span class="sxs-lookup"><span data-stu-id="2b078-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b078-111">要求</span><span class="sxs-lookup"><span data-stu-id="2b078-111">Requirements</span></span>  
 <span data-ttu-id="2b078-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b078-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b078-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b078-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b078-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b078-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b078-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b078-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
