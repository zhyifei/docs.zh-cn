---
title: ICorDebugCode4::EnumerateVariableHomes 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6e4f6e7e3107516476b179b0ed718ca44bb114
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103385"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="4d25c-102">ICorDebugCode4::EnumerateVariableHomes 方法</span><span class="sxs-lookup"><span data-stu-id="4d25c-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="4d25c-103">获取对本地变量和参数的函数中的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4d25c-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d25c-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d25c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d25c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d25c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="4d25c-106">指向的地址的指针[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)接口对象，它为本地变量和函数的参数个数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4d25c-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d25c-107">备注</span><span class="sxs-lookup"><span data-stu-id="4d25c-107">Remarks</span></span>  
 <span data-ttu-id="4d25c-108">[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)接口对象是派生自"ICorDebugEnum"接口，可用于枚举的标准枚举数[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="4d25c-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="4d25c-109">集合可能包括多个[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)对象相同的或自变量槽索引; 如果它们具有不同的函数中的不同点的家庭。</span><span class="sxs-lookup"><span data-stu-id="4d25c-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d25c-110">要求</span><span class="sxs-lookup"><span data-stu-id="4d25c-110">Requirements</span></span>  
 <span data-ttu-id="4d25c-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d25c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d25c-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d25c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d25c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d25c-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4d25c-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4d25c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d25c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d25c-115">See also</span></span>

- [<span data-ttu-id="4d25c-116">ICorDebugCode4 接口</span><span class="sxs-lookup"><span data-stu-id="4d25c-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="4d25c-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d25c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
