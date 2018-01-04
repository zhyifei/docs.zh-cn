---
title: "ICorDebugVariableHome 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a561360e7ea43945a3e12a73daba5063b3ad02f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="14e4c-102">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="14e4c-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="14e4c-103">表示本地变量或函数参数。</span><span class="sxs-lookup"><span data-stu-id="14e4c-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14e4c-104">方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-104">Methods</span></span>  
  
|<span data-ttu-id="14e4c-105">方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-105">Method</span></span>|<span data-ttu-id="14e4c-106">描述</span><span class="sxs-lookup"><span data-stu-id="14e4c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14e4c-107">GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="14e4c-108">获取函数自变量的索引。</span><span class="sxs-lookup"><span data-stu-id="14e4c-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="14e4c-109">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="14e4c-110">获取包含此"icor 调试代码"实例`ICorDebugVariableHome`对象。</span><span class="sxs-lookup"><span data-stu-id="14e4c-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="14e4c-111">GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="14e4c-112">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="14e4c-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="14e4c-113">GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="14e4c-114">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="14e4c-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="14e4c-115">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="14e4c-116">获取从基寄存器变量的偏移量。</span><span class="sxs-lookup"><span data-stu-id="14e4c-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="14e4c-117">GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="14e4c-118">获取包含的位置类型的变量的寄存器`VLT_REGISTER`，和的变量的位置类型的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="14e4c-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="14e4c-119">GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="14e4c-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="14e4c-120">获取本地变量的托管的槽索引。</span><span class="sxs-lookup"><span data-stu-id="14e4c-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14e4c-121">示例</span><span class="sxs-lookup"><span data-stu-id="14e4c-121">Example</span></span>  
 <span data-ttu-id="14e4c-122">下面的代码片段使用[ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)对象名为`pCode4`。</span><span class="sxs-lookup"><span data-stu-id="14e4c-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="14e4c-123">惠?</span><span class="sxs-lookup"><span data-stu-id="14e4c-123">Requirements</span></span>  
 <span data-ttu-id="14e4c-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14e4c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e4c-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e4c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e4c-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e4c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e4c-127">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e4c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e4c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="14e4c-128">See Also</span></span>  
 [<span data-ttu-id="14e4c-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="14e4c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="14e4c-130">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="14e4c-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
