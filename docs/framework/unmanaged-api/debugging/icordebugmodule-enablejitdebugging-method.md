---
title: "ICorDebugModule::EnableJITDebugging 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableJITDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31fc3b7c2b977dbfd6f10cc767f81748243dfce4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="4f136-102">ICorDebugModule::EnableJITDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="4f136-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="4f136-103">控制是否在实时 (JIT) 编译器会保留为此模块中的方法的调试信息。</span><span class="sxs-lookup"><span data-stu-id="4f136-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f136-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f136-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f136-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f136-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="4f136-106">[in]将此值设置为`true`启用 JIT 编译器，若要保留的 Microsoft 中间语言 (MSIL) 版本与此模块中的每个方法的 JIT 编译版本之间的映射信息。</span><span class="sxs-lookup"><span data-stu-id="4f136-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="4f136-107">[in]将此值设置为`true`启用 JIT 编译器生成使用用于调试的某些特定于 JIT 优化代码。</span><span class="sxs-lookup"><span data-stu-id="4f136-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f136-108">备注</span><span class="sxs-lookup"><span data-stu-id="4f136-108">Remarks</span></span>  
 <span data-ttu-id="4f136-109">默认情况下，调试器处于活动状态时加载的所有模块的情况下，启用 JIT 调试。</span><span class="sxs-lookup"><span data-stu-id="4f136-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="4f136-110">以编程方式启用或禁用设置重写全局设置。</span><span class="sxs-lookup"><span data-stu-id="4f136-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f136-111">要求</span><span class="sxs-lookup"><span data-stu-id="4f136-111">Requirements</span></span>  
 <span data-ttu-id="4f136-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f136-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f136-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f136-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f136-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f136-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f136-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f136-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
