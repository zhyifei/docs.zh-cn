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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10e7da7711cd63579589fda416d0d3a4f777eefe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412534"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="cba80-102">ICorDebugModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="cba80-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="cba80-103">获取模块的基址。</span><span class="sxs-lookup"><span data-stu-id="cba80-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba80-104">语法</span><span class="sxs-lookup"><span data-stu-id="cba80-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cba80-105">参数</span><span class="sxs-lookup"><span data-stu-id="cba80-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="cba80-106">[out]A `CORDB_ADDRESS` ，它指定模块的基址。</span><span class="sxs-lookup"><span data-stu-id="cba80-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cba80-107">备注</span><span class="sxs-lookup"><span data-stu-id="cba80-107">Remarks</span></span>  
 <span data-ttu-id="cba80-108">如果该模块是一个本机映像 （即，如果该模块由本机映像生成器 NGen.exe 生成），其基址将为零。</span><span class="sxs-lookup"><span data-stu-id="cba80-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cba80-109">要求</span><span class="sxs-lookup"><span data-stu-id="cba80-109">Requirements</span></span>  
 <span data-ttu-id="cba80-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cba80-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba80-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cba80-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cba80-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cba80-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cba80-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba80-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba80-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cba80-114">See Also</span></span>  
    
 
