---
title: ICorDebugAppDomain::EnumerateAssemblies 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13137dcf7c2edd96397916cc7db905c9e48a3d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401595"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="23679-102">ICorDebugAppDomain::EnumerateAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="23679-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="23679-103">应用程序域中获取程序集的枚举数。</span><span class="sxs-lookup"><span data-stu-id="23679-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23679-104">语法</span><span class="sxs-lookup"><span data-stu-id="23679-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23679-105">参数</span><span class="sxs-lookup"><span data-stu-id="23679-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="23679-106">[out]指向一个 ICorDebugAssemblyEnum 对象，它的应用程序域中的程序集的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="23679-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23679-107">要求</span><span class="sxs-lookup"><span data-stu-id="23679-107">Requirements</span></span>  
 <span data-ttu-id="23679-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23679-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23679-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23679-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23679-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23679-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23679-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23679-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
