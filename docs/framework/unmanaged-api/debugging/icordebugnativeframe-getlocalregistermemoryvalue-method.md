---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5605f7b2ad9ba42a340906559838de22ac79f789
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416675"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="c47fa-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="c47fa-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="c47fa-103">获取自变量或局部变量，其中的低位字和高位字存储在内存位置和为此本机帧分别指定寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="c47fa-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c47fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="c47fa-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c47fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="c47fa-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="c47fa-106">[in]指定包含值的高位字的寄存器"CorDebugRegister"枚举的值。</span><span class="sxs-lookup"><span data-stu-id="c47fa-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="c47fa-107">[in]A`CORDB_ADDRESS`值，该值指定包含值的低位字的内存位置。</span><span class="sxs-lookup"><span data-stu-id="c47fa-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c47fa-108">[in]一个整数，指定的二进制元数据签名，这由引用的大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="c47fa-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c47fa-109">[in]A`PCCOR_SIGNATURE`值，该值指向的值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="c47fa-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c47fa-110">[out]指向表示检索到的值存储在指定的注册和内存位置的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c47fa-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c47fa-111">要求</span><span class="sxs-lookup"><span data-stu-id="c47fa-111">Requirements</span></span>  
 <span data-ttu-id="c47fa-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c47fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c47fa-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c47fa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c47fa-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c47fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c47fa-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c47fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c47fa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c47fa-116">See Also</span></span>  
 
