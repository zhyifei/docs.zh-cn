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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c44f3e369ac64773811a6aea74756783dedd2fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209458"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="5b589-102">ICorDebugNativeFrame::GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="5b589-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="5b589-103">获取参数或存储在指定的内存位置的此本机帧中的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="5b589-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b589-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b589-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b589-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b589-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5b589-106">[in]一个`CORDB_ADDRESS`值，该值指定内存位置包含的值。</span><span class="sxs-lookup"><span data-stu-id="5b589-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5b589-107">[in]一个整数，指定的二进制元数据签名的由引用大小`pvSigBlob`参数。</span><span class="sxs-lookup"><span data-stu-id="5b589-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5b589-108">[in]一个`PCCOR_SIGNATURE`指向值类型的二进制元数据签名的值。</span><span class="sxs-lookup"><span data-stu-id="5b589-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="5b589-109">[out]指向表示检索到的值存储在指定的内存位置中的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5b589-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b589-110">要求</span><span class="sxs-lookup"><span data-stu-id="5b589-110">Requirements</span></span>  
 <span data-ttu-id="5b589-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b589-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b589-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b589-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b589-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b589-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5b589-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5b589-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b589-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b589-115">See also</span></span>
