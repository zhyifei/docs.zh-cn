---
title: ICorDebugAssembly::EnumerateModules 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f763151f4e450c48eb9304936541243af06bdca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485312"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="b16f9-102">ICorDebugAssembly::EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="b16f9-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="b16f9-103">获取一个枚举器模块中包含`ICorDebugAssembly`。</span><span class="sxs-lookup"><span data-stu-id="b16f9-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="b16f9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b16f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="b16f9-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="b16f9-106">[out]ICorDebugModuleEnum 接口的枚举器的地址指针。</span><span class="sxs-lookup"><span data-stu-id="b16f9-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b16f9-107">要求</span><span class="sxs-lookup"><span data-stu-id="b16f9-107">Requirements</span></span>  
 <span data-ttu-id="b16f9-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b16f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b16f9-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b16f9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b16f9-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b16f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b16f9-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b16f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
