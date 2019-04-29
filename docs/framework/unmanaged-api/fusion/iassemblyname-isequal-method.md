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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697207"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="4a020-102">IAssemblyName::IsEqual 方法</span><span class="sxs-lookup"><span data-stu-id="4a020-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="4a020-103">确定指定[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)对象是否等于此`IAssemblyName`、 根据指定的比较标志。</span><span class="sxs-lookup"><span data-stu-id="4a020-103">Determines whether a specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a020-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a020-104">Syntax</span></span>  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a020-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a020-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="4a020-106">[in]`IAssemblyName`要将此对象`IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="4a020-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="4a020-107">[in]按位组合[ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md)影响比较的值。</span><span class="sxs-lookup"><span data-stu-id="4a020-107">[in] A bitwise combination of [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a020-108">要求</span><span class="sxs-lookup"><span data-stu-id="4a020-108">Requirements</span></span>  
 <span data-ttu-id="4a020-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a020-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a020-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4a020-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4a020-111">**NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a020-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a020-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a020-112">See also</span></span>

- [<span data-ttu-id="4a020-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="4a020-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="4a020-114">合成枚举</span><span class="sxs-lookup"><span data-stu-id="4a020-114">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
