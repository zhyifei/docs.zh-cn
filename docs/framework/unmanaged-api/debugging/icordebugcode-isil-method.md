---
title: ICorDebugCode::IsIL 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a82606d90444c2d543065287780e42da4f8b4943
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180682"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0890f-102">ICorDebugCode::IsIL 方法</span><span class="sxs-lookup"><span data-stu-id="0890f-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="0890f-103">获取一个值，该值指示是否此"ICorDebugCode"表示 Microsoft 中间语言 (MSIL) 编译的代码。</span><span class="sxs-lookup"><span data-stu-id="0890f-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0890f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0890f-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0890f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0890f-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="0890f-106">[out]`true`如果此`ICorDebugCode`表示的代码在 MSIL 中编译; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="0890f-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0890f-107">要求</span><span class="sxs-lookup"><span data-stu-id="0890f-107">Requirements</span></span>  
 <span data-ttu-id="0890f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0890f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0890f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0890f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0890f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0890f-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0890f-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0890f-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0890f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0890f-112">See also</span></span>
