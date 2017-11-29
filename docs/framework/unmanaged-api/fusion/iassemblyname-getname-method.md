---
title: "IAssemblyName::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 612efc9d5334fd34cc61f2243914de59370c45a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="f8231-102">IAssemblyName::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="f8231-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="f8231-103">获取此引用的程序集的简单、 非加密名称[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f8231-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8231-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8231-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8231-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8231-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="f8231-106">[在中，out]大小`pwzName`以宽字符为单位，包括 null 终止符字符。</span><span class="sxs-lookup"><span data-stu-id="f8231-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="f8231-107">[out]缓冲区以保存引用程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="f8231-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8231-108">要求</span><span class="sxs-lookup"><span data-stu-id="f8231-108">Requirements</span></span>  
 <span data-ttu-id="f8231-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8231-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8231-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f8231-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f8231-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8231-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8231-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8231-112">See Also</span></span>  
 [<span data-ttu-id="f8231-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="f8231-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
