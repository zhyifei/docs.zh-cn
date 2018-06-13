---
title: ICorDebugILFrame2::EnumerateTypeParameters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a0c23c066a6f704c4dfcfbe254e91ab3bc5817e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416236"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="6e832-102">ICorDebugILFrame2::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="6e832-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="6e832-103">获取一个包含的 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="6e832-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e832-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e832-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e832-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e832-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="6e832-106">指向一个允许的类型参数的枚举的 ICorDebugTypeEnum 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6e832-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="6e832-107">类型参数列表包含的类类型参数 （如果有） 跟方法类型参数 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="6e832-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e832-108">备注</span><span class="sxs-lookup"><span data-stu-id="6e832-108">Remarks</span></span>  
 <span data-ttu-id="6e832-109">使用[imetadataimport2:: Enumgenericparams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)方法来确定类型的参数，此列表包含的多少类类型参数和方法。</span><span class="sxs-lookup"><span data-stu-id="6e832-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="6e832-110">类型参数不是始终可用的。</span><span class="sxs-lookup"><span data-stu-id="6e832-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e832-111">要求</span><span class="sxs-lookup"><span data-stu-id="6e832-111">Requirements</span></span>  
 <span data-ttu-id="6e832-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e832-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e832-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e832-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e832-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e832-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e832-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e832-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
