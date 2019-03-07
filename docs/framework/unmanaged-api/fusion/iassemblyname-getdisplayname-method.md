---
title: IAssemblyName::GetDisplayName 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddcfe7a4066686da918cf5ed93aebec0d6f306f5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482036"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="7b6b8-102">IAssemblyName::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="7b6b8-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="7b6b8-103">获取此引用的程序集的用户可读名称[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="7b6b8-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6b8-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b6b8-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b6b8-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b6b8-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="7b6b8-106">[out]包含被引用程序集的名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7b6b8-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="7b6b8-107">[in、 out]大小`szDisplayName`以宽字符，包括 null 终止符字符。</span><span class="sxs-lookup"><span data-stu-id="7b6b8-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="7b6b8-108">[in]按位组合[ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md)影响的功能值`szDisplayName`。</span><span class="sxs-lookup"><span data-stu-id="7b6b8-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b6b8-109">要求</span><span class="sxs-lookup"><span data-stu-id="7b6b8-109">Requirements</span></span>  
 <span data-ttu-id="7b6b8-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b6b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b6b8-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7b6b8-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7b6b8-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6b8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6b8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b6b8-113">See also</span></span>
- [<span data-ttu-id="7b6b8-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="7b6b8-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="7b6b8-115">合成枚举</span><span class="sxs-lookup"><span data-stu-id="7b6b8-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
