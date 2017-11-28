---
title: "ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 46d366f27c7b7eec8018f2095388fef4e6204205
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="58002-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="58002-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="58002-103">获取公共语言运行时 (CLR) 用于选择正确的预编译的标志设置的当前编译器 (即，本机) 图像加载到此过程。</span><span class="sxs-lookup"><span data-stu-id="58002-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58002-104">语法</span><span class="sxs-lookup"><span data-stu-id="58002-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58002-105">参数</span><span class="sxs-lookup"><span data-stu-id="58002-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="58002-106">[out]指向的按位组合的[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)用于选择正确的预编译的映像要加载的枚举值。</span><span class="sxs-lookup"><span data-stu-id="58002-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58002-107">备注</span><span class="sxs-lookup"><span data-stu-id="58002-107">Remarks</span></span>  
 <span data-ttu-id="58002-108">使用[icordebugprocess2:: Setdesiredngencompilerflags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)方法以设置 CLR 将用于选择正确的预编译的映像加载的标志。</span><span class="sxs-lookup"><span data-stu-id="58002-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58002-109">要求</span><span class="sxs-lookup"><span data-stu-id="58002-109">Requirements</span></span>  
 <span data-ttu-id="58002-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58002-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58002-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58002-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58002-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58002-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58002-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58002-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
