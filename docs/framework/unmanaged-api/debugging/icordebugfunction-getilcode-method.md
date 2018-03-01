---
title: "ICorDebugFunction::GetILCode 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba960246c5aa1057df517d776819817d777402f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="790be-102">ICorDebugFunction::GetILCode 方法</span><span class="sxs-lookup"><span data-stu-id="790be-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="790be-103">获取表示与此 ICorDebugFunction 对象关联的 Microsoft 中间语言 (MSIL) 代码的 ICorDebugCode 实例。</span><span class="sxs-lookup"><span data-stu-id="790be-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790be-104">语法</span><span class="sxs-lookup"><span data-stu-id="790be-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="790be-105">参数</span><span class="sxs-lookup"><span data-stu-id="790be-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="790be-106">[out]指向的指针`ICorDebugCode`实例，则为 null，如果函数不编译为 MSIL。</span><span class="sxs-lookup"><span data-stu-id="790be-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="790be-107">备注</span><span class="sxs-lookup"><span data-stu-id="790be-107">Remarks</span></span>  
 <span data-ttu-id="790be-108">如果编辑并继续对该函数，允许有`GetILCode`方法将获取与此函数的公共语言运行时 (CLR) 中的代码编辑版本对应的 MSIL 代码。</span><span class="sxs-lookup"><span data-stu-id="790be-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="790be-109">惠?</span><span class="sxs-lookup"><span data-stu-id="790be-109">Requirements</span></span>  
 <span data-ttu-id="790be-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="790be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="790be-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="790be-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="790be-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="790be-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="790be-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="790be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
