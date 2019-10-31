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
ms.openlocfilehash: 132e0868426670ba61d8ee12ba7007be1a8a52de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139407"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="54978-102">ICorDebugNativeFrame::GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="54978-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="54978-103">获取为此本机帧存储在指定寄存器中的参数或局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="54978-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54978-104">语法</span><span class="sxs-lookup"><span data-stu-id="54978-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54978-105">参数</span><span class="sxs-lookup"><span data-stu-id="54978-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="54978-106">中"CorDebugRegister" 枚举的一个值，它指定包含该值的寄存器。</span><span class="sxs-lookup"><span data-stu-id="54978-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="54978-107">中一个整数，指定 `pvSigBlob` 参数引用的二进制元数据签名的大小。</span><span class="sxs-lookup"><span data-stu-id="54978-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="54978-108">中一个 `PCCOR_SIGNATURE` 值，该值指向值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="54978-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="54978-109">弄一个指向 "ICorDebugValue" 对象地址的指针，该对象表示存储在指定寄存器中的检索到的值。</span><span class="sxs-lookup"><span data-stu-id="54978-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54978-110">备注</span><span class="sxs-lookup"><span data-stu-id="54978-110">Remarks</span></span>  
 <span data-ttu-id="54978-111">`GetLocalRegisterValue` 方法可在本机框架或实时（JIT）编译的框架中使用。</span><span class="sxs-lookup"><span data-stu-id="54978-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54978-112">要求</span><span class="sxs-lookup"><span data-stu-id="54978-112">Requirements</span></span>  
 <span data-ttu-id="54978-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54978-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54978-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54978-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54978-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54978-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54978-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54978-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54978-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="54978-117">See also</span></span>
