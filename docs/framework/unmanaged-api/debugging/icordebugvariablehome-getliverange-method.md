---
title: IcorDebugVariableHome：： GetLiveRange 方法
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
ms.openlocfilehash: fb198782bb91a8301507fd6cadcffb0378230f0e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396584"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="d3d45-102">IcorDebugVariableHome：： GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="d3d45-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="d3d45-103">获取此变量的生存期的本机范围。</span><span class="sxs-lookup"><span data-stu-id="d3d45-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d45-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3d45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d45-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3d45-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="d3d45-106">弄变量首次处于活动状态的逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="d3d45-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="d3d45-107">弄紧跟在变量上一次生存点之后的逻辑偏移量。</span><span class="sxs-lookup"><span data-stu-id="d3d45-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d45-108">要求</span><span class="sxs-lookup"><span data-stu-id="d3d45-108">Requirements</span></span>  
 <span data-ttu-id="d3d45-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d45-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d45-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3d45-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3d45-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3d45-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3d45-112">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d45-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d45-113">See also</span></span>

- [<span data-ttu-id="d3d45-114">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="d3d45-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
