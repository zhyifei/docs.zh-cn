---
title: IAssemblyName::IsEqual 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134310"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="09315-102">IAssemblyName::IsEqual 方法</span><span class="sxs-lookup"><span data-stu-id="09315-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="09315-103">根据指定的比较标志，确定指定的[IAssemblyName](iassemblyname-interface.md)对象是否等于此 `IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="09315-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09315-104">语法</span><span class="sxs-lookup"><span data-stu-id="09315-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09315-105">参数</span><span class="sxs-lookup"><span data-stu-id="09315-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="09315-106">中要与此 `IAssemblyName`进行比较的 `IAssemblyName` 对象。</span><span class="sxs-lookup"><span data-stu-id="09315-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="09315-107">中影响比较的[ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md)值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="09315-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09315-108">要求</span><span class="sxs-lookup"><span data-stu-id="09315-108">Requirements</span></span>  
 <span data-ttu-id="09315-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09315-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09315-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="09315-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="09315-111">**NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09315-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09315-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="09315-112">See also</span></span>

- [<span data-ttu-id="09315-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="09315-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="09315-114">合成枚举</span><span class="sxs-lookup"><span data-stu-id="09315-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
