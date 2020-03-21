---
title: CorGenericParamAttr 枚举
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176170"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="02393-102">CorGenericParamAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="02393-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="02393-103">包含描述泛型类型的<xref:System.Type>参数的值，如调用[IMetaDataEmit2：:DefinegenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)中使用的。</span><span class="sxs-lookup"><span data-stu-id="02393-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02393-104">语法</span><span class="sxs-lookup"><span data-stu-id="02393-104">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="02393-105">成员</span><span class="sxs-lookup"><span data-stu-id="02393-105">Members</span></span>  
  
|<span data-ttu-id="02393-106">成员</span><span class="sxs-lookup"><span data-stu-id="02393-106">Member</span></span>|<span data-ttu-id="02393-107">说明</span><span class="sxs-lookup"><span data-stu-id="02393-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="02393-108">参数方差仅适用于接口和委托的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="02393-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="02393-109">指示不存在方差。</span><span class="sxs-lookup"><span data-stu-id="02393-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="02393-110">表示协方差。</span><span class="sxs-lookup"><span data-stu-id="02393-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="02393-111">表示不差异。</span><span class="sxs-lookup"><span data-stu-id="02393-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="02393-112">特殊约束可以应用于任何<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="02393-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="02393-113">指示没有约束应用于参数<xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="02393-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="02393-114">指示参数<xref:System.Type>必须是引用类型。</span><span class="sxs-lookup"><span data-stu-id="02393-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="02393-115">指示参数<xref:System.Type>必须是不能为空值的值类型。</span><span class="sxs-lookup"><span data-stu-id="02393-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="02393-116">指示<xref:System.Type>参数必须具有不需要参数的默认公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="02393-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02393-117">要求</span><span class="sxs-lookup"><span data-stu-id="02393-117">Requirements</span></span>  
 <span data-ttu-id="02393-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02393-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02393-119">**标题：** 科尔赫德</span><span class="sxs-lookup"><span data-stu-id="02393-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="02393-120">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02393-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02393-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02393-121">See also</span></span>

- [<span data-ttu-id="02393-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="02393-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
