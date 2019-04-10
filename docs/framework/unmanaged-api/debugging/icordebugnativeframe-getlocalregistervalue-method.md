---
title: ICorDebugNativeFrame::GetLocalRegisterValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53c8290271391e52176f8364b592ce6b46faf71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195938"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="b7394-102">ICorDebugNativeFrame::GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="b7394-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="b7394-103">获取参数或指定注册到此本机帧中存储的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="b7394-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7394-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7394-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7394-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7394-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="b7394-106">[in]"CorDebugRegister"枚举，指定包含值的寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="b7394-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b7394-107">[in]一个整数，指定的二进制元数据签名的由引用大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="b7394-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b7394-108">[in]一个`PCCOR_SIGNATURE`指向值类型的二进制元数据签名的值。</span><span class="sxs-lookup"><span data-stu-id="b7394-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b7394-109">[out]指向表示检索到的值存储在指定的寄存器中的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b7394-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7394-110">备注</span><span class="sxs-lookup"><span data-stu-id="b7394-110">Remarks</span></span>  
 <span data-ttu-id="b7394-111">`GetLocalRegisterValue`在本机帧或在实时 (JIT) 中，可以使用方法的编译的框架。</span><span class="sxs-lookup"><span data-stu-id="b7394-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7394-112">要求</span><span class="sxs-lookup"><span data-stu-id="b7394-112">Requirements</span></span>  
 <span data-ttu-id="b7394-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7394-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7394-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7394-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7394-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7394-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b7394-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b7394-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7394-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7394-117">See also</span></span>
