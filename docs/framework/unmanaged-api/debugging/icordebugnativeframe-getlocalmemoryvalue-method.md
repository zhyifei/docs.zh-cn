---
title: ICorDebugNativeFrame::GetLocalMemoryValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: cee095003c136142052b8f946fa8227927c80ee2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096870"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="9f216-102">ICorDebugNativeFrame::GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="9f216-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="9f216-103">获取在此本机帧的指定内存位置中存储的参数或局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="9f216-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f216-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f216-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f216-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f216-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9f216-106">中一个 `CORDB_ADDRESS` 值，该值指定包含值的内存位置。</span><span class="sxs-lookup"><span data-stu-id="9f216-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9f216-107">中一个整数，指定 `pvSigBlob` 参数引用的二进制元数据签名的大小。</span><span class="sxs-lookup"><span data-stu-id="9f216-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9f216-108">中一个 `PCCOR_SIGNATURE` 值，该值指向值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="9f216-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9f216-109">弄一个指向 "ICorDebugValue" 对象地址的指针，该对象表示存储在指定内存位置中的检索到的值。</span><span class="sxs-lookup"><span data-stu-id="9f216-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f216-110">要求</span><span class="sxs-lookup"><span data-stu-id="9f216-110">Requirements</span></span>  
 <span data-ttu-id="9f216-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f216-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f216-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f216-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f216-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f216-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f216-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f216-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f216-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f216-115">See also</span></span>
