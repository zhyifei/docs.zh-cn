---
title: "ICorDebugCode::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69c28cba90c8ebef1b178263c8edac2cb5914c0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="70eb0-102">ICorDebugCode::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="70eb0-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="70eb0-103">获取的大小，以字节为单位表示此"icor 调试代码"的二进制代码。</span><span class="sxs-lookup"><span data-stu-id="70eb0-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70eb0-104">语法</span><span class="sxs-lookup"><span data-stu-id="70eb0-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70eb0-105">参数</span><span class="sxs-lookup"><span data-stu-id="70eb0-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="70eb0-106">[out]指向以字节为单位的二进制文件的大小的指针代码此`ICorDebugCode`对象所表示。</span><span class="sxs-lookup"><span data-stu-id="70eb0-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70eb0-107">惠?</span><span class="sxs-lookup"><span data-stu-id="70eb0-107">Requirements</span></span>  
 <span data-ttu-id="70eb0-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70eb0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70eb0-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70eb0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70eb0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70eb0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70eb0-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70eb0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70eb0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="70eb0-112">See Also</span></span>  
 
