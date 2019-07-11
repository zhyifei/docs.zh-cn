---
title: ICorDebugModule::GetEditAndContinueSnapshot 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetEditAndContinueSnapshot
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetEditAndContinueSnapshot
helpviewer_keywords:
- ICorDebugModule::GetEditAndContinueSnapshot method [.NET Framework debugging]
- GetEditAndContinueSnapshot method [.NET Framework debugging]
ms.assetid: fad94e1e-78be-440f-aa43-e0c66e0b102e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb57f6e1f87b9baf61de781033d7d8bfe1639684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762637"
---
# <a name="icordebugmodulegeteditandcontinuesnapshot-method"></a><span data-ttu-id="e65cd-102">ICorDebugModule::GetEditAndContinueSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="e65cd-102">ICorDebugModule::GetEditAndContinueSnapshot Method</span></span>
<span data-ttu-id="e65cd-103">已否决。</span><span class="sxs-lookup"><span data-stu-id="e65cd-103">Deprecated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="e65cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEditAndContinueSnapshot(  
    [out] ICorDebugEditAndContinueSnapshot **ppEditAndContinueSnapshot  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e65cd-105">要求</span><span class="sxs-lookup"><span data-stu-id="e65cd-105">Requirements</span></span>  
 <span data-ttu-id="e65cd-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e65cd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e65cd-107">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e65cd-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e65cd-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e65cd-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e65cd-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e65cd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
