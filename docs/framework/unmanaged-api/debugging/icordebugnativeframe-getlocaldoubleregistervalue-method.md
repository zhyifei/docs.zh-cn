---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13e1e3369c4e7a185c2167facc8514b5cfc85a85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115864"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="875cc-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="875cc-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="875cc-103">获取参数或此本机框架的两个指定寄存器中存储的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="875cc-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="875cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="875cc-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="875cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="875cc-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="875cc-106">[in]"CorDebugRegister"枚举，指定包含值的高位字的寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="875cc-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="875cc-107">[in]值为`CorDebugRegister`枚举，用于指定包含值的低位字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="875cc-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="875cc-108">[in]一个整数，指定的二进制元数据签名的由引用大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="875cc-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="875cc-109">[in]一个`PCCOR_SIGNATURE`指向值类型的二进制元数据签名的值。</span><span class="sxs-lookup"><span data-stu-id="875cc-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="875cc-110">[out]指向表示检索到的值存储在指定寄存器中的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="875cc-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="875cc-111">备注</span><span class="sxs-lookup"><span data-stu-id="875cc-111">Remarks</span></span>  
 <span data-ttu-id="875cc-112">`GetLocalDoubleRegisterValue`在本机帧或在实时 (JIT) 中，可以使用方法的编译的框架。</span><span class="sxs-lookup"><span data-stu-id="875cc-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="875cc-113">要求</span><span class="sxs-lookup"><span data-stu-id="875cc-113">Requirements</span></span>  
 <span data-ttu-id="875cc-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="875cc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="875cc-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="875cc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="875cc-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="875cc-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="875cc-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="875cc-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="875cc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="875cc-118">See also</span></span>
