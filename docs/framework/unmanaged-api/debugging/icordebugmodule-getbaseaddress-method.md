---
title: ICorDebugModule::GetBaseAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: 9270afa1d8c8ddd74cfe6dd05e39c1480f5767e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206936"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="3c7b1-102">ICorDebugModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="3c7b1-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="3c7b1-103">获取模块的基址。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c7b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c7b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c7b1-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="3c7b1-106">弄一个 `CORDB_ADDRESS` ，它指定模块的基址。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c7b1-107">备注</span><span class="sxs-lookup"><span data-stu-id="3c7b1-107">Remarks</span></span>  
 <span data-ttu-id="3c7b1-108">如果模块是本机映像（即，如果模块是由本机映像生成器 Ngen.exe 生成的），则其基址将为零。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c7b1-109">要求</span><span class="sxs-lookup"><span data-stu-id="3c7b1-109">Requirements</span></span>  
 <span data-ttu-id="3c7b1-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c7b1-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c7b1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c7b1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c7b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c7b1-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c7b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7b1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c7b1-114">See also</span></span>
