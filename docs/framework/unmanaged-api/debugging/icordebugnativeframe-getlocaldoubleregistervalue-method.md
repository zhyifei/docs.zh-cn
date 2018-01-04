---
title: "ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece07fcffbc0d0e6b8cf06cc04866c1b651e6a01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="a3594-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="a3594-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="a3594-103">获取自变量或此本机帧的两个指定寄存器中存储的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="a3594-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3594-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3594-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3594-105">参数</span><span class="sxs-lookup"><span data-stu-id="a3594-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="a3594-106">[in]指定包含值的高位字的寄存器"CorDebugRegister"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="a3594-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="a3594-107">[in]值为`CorDebugRegister`枚举，它指定包含值的低位字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="a3594-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a3594-108">[in]一个整数，指定的二进制元数据签名，这由引用的大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="a3594-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a3594-109">[in]A`PCCOR_SIGNATURE`值，该值指向的值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="a3594-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a3594-110">[out]指向表示检索到的值存储在指定的寄存器中的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a3594-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3594-111">备注</span><span class="sxs-lookup"><span data-stu-id="a3594-111">Remarks</span></span>  
 <span data-ttu-id="a3594-112">`GetLocalDoubleRegisterValue`方法可用于在本机框架或在实时 (JIT) 中的编译的框架。</span><span class="sxs-lookup"><span data-stu-id="a3594-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3594-113">惠?</span><span class="sxs-lookup"><span data-stu-id="a3594-113">Requirements</span></span>  
 <span data-ttu-id="a3594-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a3594-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3594-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3594-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3594-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3594-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3594-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3594-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3594-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3594-118">See Also</span></span>  
 
