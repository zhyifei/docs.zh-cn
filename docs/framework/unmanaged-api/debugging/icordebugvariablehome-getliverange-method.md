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
ms.openlocfilehash: 7e2c9e981f431bb87df61a71389abf3d42a6a507
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986734"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="adbc2-102">IcorDebugVariableHome::GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="adbc2-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="adbc2-103">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="adbc2-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="adbc2-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adbc2-105">参数</span><span class="sxs-lookup"><span data-stu-id="adbc2-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="adbc2-106">[out]在该变量是第一个实时逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="adbc2-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="adbc2-107">[out]立即后的变量是最后一个实时的点的逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="adbc2-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adbc2-108">要求</span><span class="sxs-lookup"><span data-stu-id="adbc2-108">Requirements</span></span>  
 <span data-ttu-id="adbc2-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="adbc2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adbc2-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adbc2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adbc2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adbc2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adbc2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adbc2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbc2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="adbc2-113">See also</span></span>

- [<span data-ttu-id="adbc2-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="adbc2-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
