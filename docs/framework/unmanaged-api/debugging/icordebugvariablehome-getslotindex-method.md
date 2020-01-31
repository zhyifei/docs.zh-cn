---
title: ICorDebugVariableHome：： GetSlotIndex 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790972"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="aea9e-102">ICorDebugVariableHome：： GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="aea9e-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="aea9e-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="aea9e-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="aea9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aea9e-105">参数</span><span class="sxs-lookup"><span data-stu-id="aea9e-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="aea9e-106">弄指向局部变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="aea9e-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aea9e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="aea9e-107">Return Value</span></span>  
 <span data-ttu-id="aea9e-108">方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="aea9e-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="aea9e-109">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="aea9e-109">Value</span></span>|<span data-ttu-id="aea9e-110">描述</span><span class="sxs-lookup"><span data-stu-id="aea9e-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="aea9e-111">方法调用在 `pSlotIndex`中返回槽索引值。</span><span class="sxs-lookup"><span data-stu-id="aea9e-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="aea9e-112">当前[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例表示函数参数。</span><span class="sxs-lookup"><span data-stu-id="aea9e-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aea9e-113">备注</span><span class="sxs-lookup"><span data-stu-id="aea9e-113">Remarks</span></span>  
 <span data-ttu-id="aea9e-114">槽索引可用于检索此局部变量的元数据。</span><span class="sxs-lookup"><span data-stu-id="aea9e-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aea9e-115">需求</span><span class="sxs-lookup"><span data-stu-id="aea9e-115">Requirements</span></span>  
 <span data-ttu-id="aea9e-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aea9e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aea9e-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aea9e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aea9e-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aea9e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aea9e-119">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aea9e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea9e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aea9e-120">See also</span></span>

- [<span data-ttu-id="aea9e-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="aea9e-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
