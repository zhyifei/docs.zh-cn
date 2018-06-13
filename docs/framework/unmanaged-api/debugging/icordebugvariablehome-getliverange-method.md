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
ms.openlocfilehash: c0f9c586a9e95fc2e57c4956601f6dce2b988159
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423060"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="34f21-102">IcorDebugVariableHome::GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="34f21-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="34f21-103">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="34f21-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f21-104">语法</span><span class="sxs-lookup"><span data-stu-id="34f21-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34f21-105">参数</span><span class="sxs-lookup"><span data-stu-id="34f21-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="34f21-106">[out]从该处的变量是第一个实时逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="34f21-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="34f21-107">[out]从该处的变量是最后一个实时点后立即逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="34f21-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f21-108">要求</span><span class="sxs-lookup"><span data-stu-id="34f21-108">Requirements</span></span>  
 <span data-ttu-id="34f21-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34f21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f21-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34f21-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f21-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34f21-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f21-112">**.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f21-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="34f21-113">See Also</span></span>  
 [<span data-ttu-id="34f21-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="34f21-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
