---
title: ICorDebugILCode2::GetLocalVarSigToken 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3759cfa330ac37d2ed62a0b8bb70b5e10cd9d12e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782449"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="77e43-102">ICorDebugILCode2::GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="77e43-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="77e43-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="77e43-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="77e43-104">获取元数据标记，用于由此实例表示的函数的局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="77e43-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e43-105">语法</span><span class="sxs-lookup"><span data-stu-id="77e43-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77e43-106">参数</span><span class="sxs-lookup"><span data-stu-id="77e43-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="77e43-107">[out] 指向此函数的局部变量签名的 `mdSignature` 标记，或者指向 `mdSignatureNil`（如果不存在签名，即该函数没有任何局部变量）的指针。</span><span class="sxs-lookup"><span data-stu-id="77e43-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77e43-108">备注</span><span class="sxs-lookup"><span data-stu-id="77e43-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77e43-109">需求</span><span class="sxs-lookup"><span data-stu-id="77e43-109">Requirements</span></span>  
 <span data-ttu-id="77e43-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77e43-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77e43-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77e43-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77e43-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77e43-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77e43-113">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77e43-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e43-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77e43-114">See also</span></span>

- [<span data-ttu-id="77e43-115">ICorDebugILCode2 接口</span><span class="sxs-lookup"><span data-stu-id="77e43-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="77e43-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="77e43-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
