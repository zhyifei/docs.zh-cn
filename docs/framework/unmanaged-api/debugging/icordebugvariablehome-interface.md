---
title: ICorDebugVariableHome 接口
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339a0f502b7e47f7bee82a0da92185481d909e64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202906"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="4990c-102">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="4990c-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="4990c-103">表示本地变量或函数的参数。</span><span class="sxs-lookup"><span data-stu-id="4990c-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4990c-104">方法</span><span class="sxs-lookup"><span data-stu-id="4990c-104">Methods</span></span>  
  
|<span data-ttu-id="4990c-105">方法</span><span class="sxs-lookup"><span data-stu-id="4990c-105">Method</span></span>|<span data-ttu-id="4990c-106">描述</span><span class="sxs-lookup"><span data-stu-id="4990c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4990c-107">GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="4990c-108">获取函数参数的索引。</span><span class="sxs-lookup"><span data-stu-id="4990c-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="4990c-109">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="4990c-110">获取包含此"ICorDebugCode"实例`ICorDebugVariableHome`对象。</span><span class="sxs-lookup"><span data-stu-id="4990c-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="4990c-111">GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="4990c-112">获取对其此变量是实时的本机范围。</span><span class="sxs-lookup"><span data-stu-id="4990c-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="4990c-113">GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="4990c-114">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="4990c-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="4990c-115">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="4990c-116">获取从基寄存器变量的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4990c-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="4990c-117">GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="4990c-118">获取包含的位置类型的变量的寄存器`VLT_REGISTER`，并与位置类型的变量的基寄存器`VLT_REGISTER_RELATIVE`。</span><span class="sxs-lookup"><span data-stu-id="4990c-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="4990c-119">GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="4990c-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="4990c-120">获取本地变量的托管的槽索引。</span><span class="sxs-lookup"><span data-stu-id="4990c-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4990c-121">示例</span><span class="sxs-lookup"><span data-stu-id="4990c-121">Example</span></span>  
 <span data-ttu-id="4990c-122">使用下面的代码段[ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)名为对象`pCode4`。</span><span class="sxs-lookup"><span data-stu-id="4990c-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="4990c-123">要求</span><span class="sxs-lookup"><span data-stu-id="4990c-123">Requirements</span></span>  
 <span data-ttu-id="4990c-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4990c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4990c-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4990c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4990c-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4990c-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4990c-127">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4990c-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4990c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4990c-128">See also</span></span>

- [<span data-ttu-id="4990c-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="4990c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4990c-130">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4990c-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
