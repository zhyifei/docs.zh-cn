---
title: "IAssemblyName::GetVersion 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetVersion
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a843ca1ebc12b0ae9aaf1d9dbb4e5d845fb61fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="7d895-102">IAssemblyName::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="7d895-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="7d895-103">获取此引用的程序集的版本信息[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="7d895-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d895-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d895-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d895-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d895-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="7d895-106">[out]版本的高 32 位。</span><span class="sxs-lookup"><span data-stu-id="7d895-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="7d895-107">[out]版本的低 32 位。</span><span class="sxs-lookup"><span data-stu-id="7d895-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d895-108">要求</span><span class="sxs-lookup"><span data-stu-id="7d895-108">Requirements</span></span>  
 <span data-ttu-id="7d895-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d895-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d895-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7d895-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7d895-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d895-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d895-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d895-112">See Also</span></span>  
 [<span data-ttu-id="7d895-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="7d895-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
