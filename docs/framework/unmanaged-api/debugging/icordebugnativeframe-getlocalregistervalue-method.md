---
title: "ICorDebugNativeFrame::GetLocalRegisterValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 43fdfc5cf4f17aaa9b26fc4a028c98c63a1b3c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="fed78-102">ICorDebugNativeFrame::GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="fed78-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="fed78-103">获取自变量或存储在指定此本机帧的寄存器中的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="fed78-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed78-104">语法</span><span class="sxs-lookup"><span data-stu-id="fed78-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fed78-105">参数</span><span class="sxs-lookup"><span data-stu-id="fed78-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="fed78-106">[in]指定包含的值的寄存器"CorDebugRegister"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="fed78-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fed78-107">[in]一个整数，指定的二进制元数据签名，这由引用的大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="fed78-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="fed78-108">[in]A`PCCOR_SIGNATURE`值，该值指向的值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="fed78-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fed78-109">[out]指向表示检索到的值存储在指定的寄存器中的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="fed78-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fed78-110">备注</span><span class="sxs-lookup"><span data-stu-id="fed78-110">Remarks</span></span>  
 <span data-ttu-id="fed78-111">`GetLocalRegisterValue`方法可用于在本机框架或在实时 (JIT) 中的编译的框架。</span><span class="sxs-lookup"><span data-stu-id="fed78-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed78-112">要求</span><span class="sxs-lookup"><span data-stu-id="fed78-112">Requirements</span></span>  
 <span data-ttu-id="fed78-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fed78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fed78-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fed78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fed78-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fed78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fed78-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fed78-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed78-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fed78-117">See Also</span></span>  
 
