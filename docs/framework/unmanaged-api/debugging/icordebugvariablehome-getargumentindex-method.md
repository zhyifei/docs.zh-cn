---
title: ICorDebugVariableHome::GetArgumentIndex 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163704bf9a71ceda04bdfd73f9ca676c19d8a62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526635"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="ee23b-102">ICorDebugVariableHome::GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="ee23b-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="ee23b-103">获取函数参数的索引。</span><span class="sxs-lookup"><span data-stu-id="ee23b-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee23b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee23b-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee23b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee23b-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="ee23b-106">[out]指向参数索引的指针。</span><span class="sxs-lookup"><span data-stu-id="ee23b-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee23b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ee23b-107">Return Value</span></span>  
 <span data-ttu-id="ee23b-108">该方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="ee23b-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ee23b-109">“值”</span><span class="sxs-lookup"><span data-stu-id="ee23b-109">Value</span></span>|<span data-ttu-id="ee23b-110">描述</span><span class="sxs-lookup"><span data-stu-id="ee23b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ee23b-111">方法调用返回了有效的参数索引。</span><span class="sxs-lookup"><span data-stu-id="ee23b-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ee23b-112">当前[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)实例表示的本地变量。</span><span class="sxs-lookup"><span data-stu-id="ee23b-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee23b-113">备注</span><span class="sxs-lookup"><span data-stu-id="ee23b-113">Remarks</span></span>  
 <span data-ttu-id="ee23b-114">可以使用的参数索引检索此参数的元数据。</span><span class="sxs-lookup"><span data-stu-id="ee23b-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee23b-115">要求</span><span class="sxs-lookup"><span data-stu-id="ee23b-115">Requirements</span></span>  
 <span data-ttu-id="ee23b-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee23b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee23b-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee23b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee23b-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee23b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee23b-119">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee23b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee23b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee23b-120">See also</span></span>
- [<span data-ttu-id="ee23b-121">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="ee23b-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
