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
ms.openlocfilehash: 2bbaa05d767302bcd75303ec902a82e7992e1db3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="8a0b3-102">ICorPublishProcess::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="8a0b3-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="8a0b3-103">获取引用此进程可执行文件的完整路径[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a0b3-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a0b3-105">参数</span><span class="sxs-lookup"><span data-stu-id="8a0b3-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8a0b3-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8a0b3-107">[out]在中返回的宽字符数`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="8a0b3-108">[out]用于存储文件的名称，包括可执行文件的完整路径的数组。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="8a0b3-109">名称是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a0b3-110">要求</span><span class="sxs-lookup"><span data-stu-id="8a0b3-110">Requirements</span></span>  
 <span data-ttu-id="8a0b3-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a0b3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a0b3-112">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8a0b3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8a0b3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a0b3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a0b3-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a0b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0b3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a0b3-115">See Also</span></span>  
 [<span data-ttu-id="8a0b3-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="8a0b3-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
