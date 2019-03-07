---
title: ICorDebugFunction::GetLocalVarSigToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a682999c888a93cef94162a8179673c862dc43ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476641"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="0eb05-102">ICorDebugFunction::GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="0eb05-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="0eb05-103">获取此 ICorDebugFunction 实例所表示的函数的局部变量签名的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="0eb05-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb05-104">语法</span><span class="sxs-lookup"><span data-stu-id="0eb05-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb05-105">参数</span><span class="sxs-lookup"><span data-stu-id="0eb05-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="0eb05-106">[out]一个指向`mdSignature`标记，表示此函数的局部变量签名或`mdSignatureNil`，则此函数没有任何本地变量。</span><span class="sxs-lookup"><span data-stu-id="0eb05-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb05-107">要求</span><span class="sxs-lookup"><span data-stu-id="0eb05-107">Requirements</span></span>  
 <span data-ttu-id="0eb05-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0eb05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eb05-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eb05-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eb05-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eb05-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eb05-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eb05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
