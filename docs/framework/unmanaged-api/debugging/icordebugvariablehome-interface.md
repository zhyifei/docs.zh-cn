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
ms.openlocfilehash: c347346c9157fea843527c662e26ffcfba22ace4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790957"
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="fc9f9-102">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="fc9f9-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="fc9f9-103">表示函数的局部变量或自变量。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc9f9-104">方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-104">Methods</span></span>  
  
|<span data-ttu-id="fc9f9-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-105">Method</span></span>|<span data-ttu-id="fc9f9-106">描述</span><span class="sxs-lookup"><span data-stu-id="fc9f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc9f9-107">GetArgumentIndex 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-107">GetArgumentIndex Method</span></span>](icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="fc9f9-108">获取函数参数的索引。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="fc9f9-109">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-109">GetCode Method</span></span>](icordebugvariablehome-getcode-method.md)|<span data-ttu-id="fc9f9-110">获取包含此 `ICorDebugVariableHome` 对象的 "ICorDebugCode" 实例。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="fc9f9-111">GetLiveRange 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-111">GetLiveRange Method</span></span>](icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="fc9f9-112">获取此变量的生存期的本机范围。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="fc9f9-113">GetLocationType 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-113">GetLocationType Method</span></span>](icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="fc9f9-114">获取变量的本机位置的类型。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="fc9f9-115">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-115">GetOffset Method</span></span>](icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="fc9f9-116">获取与基寄存器相对应的偏移量。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="fc9f9-117">GetRegister 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-117">GetRegister Method</span></span>](icordebugvariablehome-getregister-method.md)|<span data-ttu-id="fc9f9-118">获取一个寄存器，其中包含位置类型为 `VLT_REGISTER`的变量，以及位置类型为 `VLT_REGISTER_RELATIVE`的变量的基寄存器。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="fc9f9-119">GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="fc9f9-119">GetSlotIndex Method</span></span>](icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="fc9f9-120">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc9f9-121">示例</span><span class="sxs-lookup"><span data-stu-id="fc9f9-121">Example</span></span>  
 <span data-ttu-id="fc9f9-122">下面的代码片段使用名为 `pCode4`的[ICorDebugCode4](icordebugcode4-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-122">The following code fragment uses the [ICorDebugCode4](icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="fc9f9-123">需求</span><span class="sxs-lookup"><span data-stu-id="fc9f9-123">Requirements</span></span>  
 <span data-ttu-id="fc9f9-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc9f9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc9f9-125">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc9f9-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc9f9-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc9f9-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc9f9-127">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc9f9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc9f9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc9f9-128">See also</span></span>

- [<span data-ttu-id="fc9f9-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="fc9f9-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc9f9-130">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="fc9f9-130">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
