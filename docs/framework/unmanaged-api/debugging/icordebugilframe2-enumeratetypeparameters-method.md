---
title: "ICorDebugILFrame2::EnumerateTypeParameters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebc2496d633c04c94e94be201956daab38b79224
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="ad13a-102">ICorDebugILFrame2::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="ad13a-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="ad13a-103">获取一个包含的 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="ad13a-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad13a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad13a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad13a-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad13a-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="ad13a-106">指向一个允许的类型参数的枚举的 ICorDebugTypeEnum 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ad13a-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="ad13a-107">类型参数列表包含的类类型参数 （如果有） 跟方法类型参数 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="ad13a-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad13a-108">备注</span><span class="sxs-lookup"><span data-stu-id="ad13a-108">Remarks</span></span>  
 <span data-ttu-id="ad13a-109">使用[imetadataimport2:: Enumgenericparams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)方法来确定类型的参数，此列表包含的多少类类型参数和方法。</span><span class="sxs-lookup"><span data-stu-id="ad13a-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="ad13a-110">类型参数不是始终可用的。</span><span class="sxs-lookup"><span data-stu-id="ad13a-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad13a-111">要求</span><span class="sxs-lookup"><span data-stu-id="ad13a-111">Requirements</span></span>  
 <span data-ttu-id="ad13a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad13a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad13a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad13a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad13a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad13a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad13a-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad13a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
