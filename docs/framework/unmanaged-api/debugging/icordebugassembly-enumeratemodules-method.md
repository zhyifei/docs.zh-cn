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
ms.openlocfilehash: b55bd41039fce84a21c5d651d93b56f5d84b7611
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088184"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="6b29f-102">ICorDebugAssembly::EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="6b29f-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="6b29f-103">获取 `ICorDebugAssembly`中包含的模块的枚举器。</span><span class="sxs-lookup"><span data-stu-id="6b29f-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b29f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b29f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b29f-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b29f-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="6b29f-106">弄一个指针，指向作为枚举器的 ICorDebugModuleEnum 接口的地址。</span><span class="sxs-lookup"><span data-stu-id="6b29f-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b29f-107">要求</span><span class="sxs-lookup"><span data-stu-id="6b29f-107">Requirements</span></span>  
 <span data-ttu-id="6b29f-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b29f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b29f-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b29f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b29f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b29f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b29f-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b29f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
