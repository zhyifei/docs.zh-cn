---
title: ICorDebugModule::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff7c77a27e9be58e9702c3a5e3f990863dc83901
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763621"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="ecf68-102">ICorDebugModule::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="ecf68-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="ecf68-103">获取包含此模块的过程。</span><span class="sxs-lookup"><span data-stu-id="ecf68-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf68-104">语法</span><span class="sxs-lookup"><span data-stu-id="ecf68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecf68-105">参数</span><span class="sxs-lookup"><span data-stu-id="ecf68-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="ecf68-106">[out]指向表示包含此模块的流程 ICorDebugProcess 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ecf68-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecf68-107">要求</span><span class="sxs-lookup"><span data-stu-id="ecf68-107">Requirements</span></span>  
 <span data-ttu-id="ecf68-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf68-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf68-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecf68-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecf68-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecf68-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecf68-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf68-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
