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
ms.openlocfilehash: ada2e0e81c9e022e152e01472839d5d506332fac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402377"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="f9d2f-102">ICorDebugAssembly::EnumerateModules 方法</span><span class="sxs-lookup"><span data-stu-id="f9d2f-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="f9d2f-103">中包含的模块中获取的枚举数`ICorDebugAssembly`。</span><span class="sxs-lookup"><span data-stu-id="f9d2f-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9d2f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9d2f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9d2f-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="f9d2f-106">[out]ICorDebugModuleEnum 接口即枚举器的地址指向的指针。</span><span class="sxs-lookup"><span data-stu-id="f9d2f-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d2f-107">要求</span><span class="sxs-lookup"><span data-stu-id="f9d2f-107">Requirements</span></span>  
 <span data-ttu-id="f9d2f-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d2f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9d2f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9d2f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9d2f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9d2f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9d2f-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9d2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
