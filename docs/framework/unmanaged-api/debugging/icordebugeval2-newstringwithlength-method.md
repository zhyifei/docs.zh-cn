---
title: ICorDebugEval2::NewStringWithLength 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a90f0a0319d88654d0310530749ef35b7095e0fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754423"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="838bd-102">ICorDebugEval2::NewStringWithLength 方法</span><span class="sxs-lookup"><span data-stu-id="838bd-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="838bd-103">使用指定的内容创建指定长度的字符串。</span><span class="sxs-lookup"><span data-stu-id="838bd-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="838bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="838bd-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="838bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="838bd-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="838bd-106">[in]指向的字符串值的指针。</span><span class="sxs-lookup"><span data-stu-id="838bd-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="838bd-107">[in]字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="838bd-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="838bd-108">备注</span><span class="sxs-lookup"><span data-stu-id="838bd-108">Remarks</span></span>  
 <span data-ttu-id="838bd-109">如果字符串的尾随预期 null 字符可在托管字符串中的调用方`NewStringWithLength`方法必须确保字符串长度包括尾随的 null 字符。</span><span class="sxs-lookup"><span data-stu-id="838bd-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="838bd-110">始终在线程当前执行的应用程序域中创建的字符串。</span><span class="sxs-lookup"><span data-stu-id="838bd-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="838bd-111">要求</span><span class="sxs-lookup"><span data-stu-id="838bd-111">Requirements</span></span>  
 <span data-ttu-id="838bd-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="838bd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="838bd-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="838bd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="838bd-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="838bd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="838bd-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="838bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
