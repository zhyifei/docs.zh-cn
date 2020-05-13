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
ms.openlocfilehash: a923701b05f7d283c4fd464d470fb0c9243c1bd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213603"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="f4965-102">ICorDebugFunction::GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="f4965-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="f4965-103">获取此 ICorDebugFunction 实例所表示的函数的局部变量签名的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f4965-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4965-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4965-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4965-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4965-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="f4965-106">弄一个指针，指向 `mdSignature` 此函数的局部变量签名的标记， `mdSignatureNil` 如果此函数没有本地变量，则为。</span><span class="sxs-lookup"><span data-stu-id="f4965-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4965-107">要求</span><span class="sxs-lookup"><span data-stu-id="f4965-107">Requirements</span></span>  
 <span data-ttu-id="f4965-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4965-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4965-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4965-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4965-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4965-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4965-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4965-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
