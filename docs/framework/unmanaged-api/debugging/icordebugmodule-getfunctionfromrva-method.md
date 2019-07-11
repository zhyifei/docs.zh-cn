---
title: ICorDebugModule::GetFunctionFromRVA 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromRVA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromRVA
helpviewer_keywords:
- GetFunctionFromRVA method [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromRVA method [.NET Framework debugging]
ms.assetid: f5a34517-2422-484f-be89-2ce0b4bce195
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ab8d56a457db0a70b47293684f0de73ce9ff5f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763372"
---
# <a name="icordebugmodulegetfunctionfromrva-method"></a><span data-ttu-id="15e89-102">ICorDebugModule::GetFunctionFromRVA 方法</span><span class="sxs-lookup"><span data-stu-id="15e89-102">ICorDebugModule::GetFunctionFromRVA Method</span></span>
<span data-ttu-id="15e89-103">当前版本的.NET Framework 中，此方法尚未实现。</span><span class="sxs-lookup"><span data-stu-id="15e89-103">This method has not been implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e89-104">语法</span><span class="sxs-lookup"><span data-stu-id="15e89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromRVA(  
    [in]  CORDB_ADDRESS      rva,  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="15e89-105">要求</span><span class="sxs-lookup"><span data-stu-id="15e89-105">Requirements</span></span>  
 <span data-ttu-id="15e89-106">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15e89-106">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e89-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="15e89-107">See also</span></span>
