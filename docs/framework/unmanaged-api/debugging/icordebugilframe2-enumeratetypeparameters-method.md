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
ms.openlocfilehash: 7454b551edc546fecbd9d091f7c821e0a07b16df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988541"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="88232-102">ICorDebugILFrame2::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="88232-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="88232-103">获取一个包含 ICorDebugTypeEnum 对象<xref:System.Type>此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="88232-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88232-104">语法</span><span class="sxs-lookup"><span data-stu-id="88232-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88232-105">参数</span><span class="sxs-lookup"><span data-stu-id="88232-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="88232-106">指向一个允许的类型参数的枚举的 ICorDebugTypeEnum 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="88232-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="88232-107">类型参数列表包含的类类型参数 （如果有） 后接方法类型参数 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="88232-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88232-108">备注</span><span class="sxs-lookup"><span data-stu-id="88232-108">Remarks</span></span>  
 <span data-ttu-id="88232-109">使用[IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)方法，以确定多少个类类型参数和方法键入此列表包含的参数。</span><span class="sxs-lookup"><span data-stu-id="88232-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="88232-110">类型参数并不总是可用。</span><span class="sxs-lookup"><span data-stu-id="88232-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88232-111">要求</span><span class="sxs-lookup"><span data-stu-id="88232-111">Requirements</span></span>  
 <span data-ttu-id="88232-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88232-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88232-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88232-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88232-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88232-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88232-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88232-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
