---
title: IcorDebugVariableHome::GetLiveRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 894629b7cc1c48eb6c1820c65a0a2a41332a8080
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549686"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="c014d-102">IcorDebugVariableHome::GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="c014d-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="c014d-103">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="c014d-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c014d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c014d-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c014d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c014d-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="c014d-106">[out]在该变量是第一个实时逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="c014d-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="c014d-107">[out]立即后的变量是最后一个实时的点的逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="c014d-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c014d-108">要求</span><span class="sxs-lookup"><span data-stu-id="c014d-108">Requirements</span></span>  
 <span data-ttu-id="c014d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c014d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c014d-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c014d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c014d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c014d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c014d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c014d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c014d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c014d-113">See also</span></span>
- [<span data-ttu-id="c014d-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="c014d-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
