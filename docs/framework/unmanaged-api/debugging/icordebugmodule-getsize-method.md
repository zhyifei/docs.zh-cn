---
title: ICorDebugModule::GetSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212511"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="d6e45-102">ICorDebugModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="d6e45-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="d6e45-103">获取模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d6e45-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e45-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6e45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6e45-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6e45-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="d6e45-106">弄模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d6e45-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="d6e45-107">如果该模块是通过本机映像生成器（Ngen.exe）生成的，则该模块的大小将为零。</span><span class="sxs-lookup"><span data-stu-id="d6e45-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e45-108">要求</span><span class="sxs-lookup"><span data-stu-id="d6e45-108">Requirements</span></span>  
 <span data-ttu-id="d6e45-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e45-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e45-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e45-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e45-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e45-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e45-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
