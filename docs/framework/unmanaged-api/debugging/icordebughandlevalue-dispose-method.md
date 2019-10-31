---
title: ICorDebugHandleValue::Dispose 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
ms.openlocfilehash: 957035591090fb5a6a615662c4840ff16509ee20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138508"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="84ace-102">ICorDebugHandleValue::Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="84ace-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="84ace-103">释放此 ICorDebugHandleValue 对象引用的句柄，无需显式释放接口指针。</span><span class="sxs-lookup"><span data-stu-id="84ace-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84ace-104">语法</span><span class="sxs-lookup"><span data-stu-id="84ace-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="84ace-105">要求</span><span class="sxs-lookup"><span data-stu-id="84ace-105">Requirements</span></span>  
 <span data-ttu-id="84ace-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84ace-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84ace-107">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84ace-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84ace-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84ace-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84ace-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84ace-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
