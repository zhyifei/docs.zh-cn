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
ms.openlocfilehash: 38f48f2d95829d2c8111065e5f4ede4e43a16d63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796662"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="e61c9-102">IAssemblyName::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="e61c9-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="e61c9-103">获取此[IAssemblyName](iassemblyname-interface.md)对象所引用的程序集的可读名称。</span><span class="sxs-lookup"><span data-stu-id="e61c9-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="e61c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e61c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="e61c9-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="e61c9-106">弄包含所引用程序集的名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e61c9-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="e61c9-107">[in，out]宽字符的`szDisplayName`大小，包括 null 终止符。</span><span class="sxs-lookup"><span data-stu-id="e61c9-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="e61c9-108">中影响的功能`szDisplayName`的[ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md)值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="e61c9-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61c9-109">要求</span><span class="sxs-lookup"><span data-stu-id="e61c9-109">Requirements</span></span>  
 <span data-ttu-id="e61c9-110">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e61c9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61c9-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="e61c9-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e61c9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61c9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61c9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e61c9-113">See also</span></span>

- [<span data-ttu-id="e61c9-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="e61c9-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="e61c9-115">合成枚举</span><span class="sxs-lookup"><span data-stu-id="e61c9-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
