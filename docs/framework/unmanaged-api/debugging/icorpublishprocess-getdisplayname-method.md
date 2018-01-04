---
title: "ICorPublishProcess::GetDisplayName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.GetDisplayName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98c751b29f1bffd8baa8b87548d588c6db98eed2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="f2ff7-102">ICorPublishProcess::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="f2ff7-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="f2ff7-103">获取引用此进程可执行文件的完整路径[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ff7-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2ff7-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2ff7-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2ff7-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f2ff7-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f2ff7-107">[out]在中返回的宽字符数`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="f2ff7-108">[out]用于存储文件的名称，包括可执行文件的完整路径的数组。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="f2ff7-109">名称是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ff7-110">惠?</span><span class="sxs-lookup"><span data-stu-id="f2ff7-110">Requirements</span></span>  
 <span data-ttu-id="f2ff7-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2ff7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ff7-112">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f2ff7-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f2ff7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2ff7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2ff7-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ff7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ff7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ff7-115">See Also</span></span>  
 [<span data-ttu-id="f2ff7-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="f2ff7-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
