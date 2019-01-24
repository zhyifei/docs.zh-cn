---
title: IAssemblyName::GetName 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7859beae572f05863fb24f0257aae8b0ec16bbcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640870"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="8ca1d-102">IAssemblyName::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="8ca1d-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="8ca1d-103">获取此引用的程序集的简单、 非加密名称[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="8ca1d-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ca1d-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ca1d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ca1d-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="8ca1d-106">[in、 out]大小`pwzName`以宽字符，包括 null 终止符字符。</span><span class="sxs-lookup"><span data-stu-id="8ca1d-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="8ca1d-107">[out]用于保存引用的程序集的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8ca1d-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca1d-108">要求</span><span class="sxs-lookup"><span data-stu-id="8ca1d-108">Requirements</span></span>  
 <span data-ttu-id="8ca1d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ca1d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ca1d-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8ca1d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8ca1d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca1d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ca1d-112">See also</span></span>
- [<span data-ttu-id="8ca1d-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="8ca1d-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
