---
title: ICorDebugCode::GetSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c5d42aa7053c1138808775a16d820d5fef3b095
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410814"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="fe0f1-102">ICorDebugCode::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="fe0f1-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="fe0f1-103">获取的大小，以字节为单位表示此"icor 调试代码"的二进制代码。</span><span class="sxs-lookup"><span data-stu-id="fe0f1-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe0f1-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe0f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe0f1-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="fe0f1-106">[out]指向以字节为单位的二进制文件的大小的指针代码此`ICorDebugCode`对象所表示。</span><span class="sxs-lookup"><span data-stu-id="fe0f1-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe0f1-107">要求</span><span class="sxs-lookup"><span data-stu-id="fe0f1-107">Requirements</span></span>  
 <span data-ttu-id="fe0f1-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe0f1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe0f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe0f1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe0f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe0f1-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe0f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0f1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe0f1-112">See Also</span></span>  
 
