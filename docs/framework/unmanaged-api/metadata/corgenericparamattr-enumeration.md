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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d56be8c6f224010da22803894524299c0d376ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443526"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="2bef9-102">CorGenericParamAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="2bef9-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="2bef9-103">包含值，用于描述<xref:System.Type>对于泛型类型，为调用中使用的参数[imetadataemit2:: Definegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2bef9-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bef9-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bef9-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="2bef9-105">成员</span><span class="sxs-lookup"><span data-stu-id="2bef9-105">Members</span></span>  
  
|<span data-ttu-id="2bef9-106">成员</span><span class="sxs-lookup"><span data-stu-id="2bef9-106">Member</span></span>|<span data-ttu-id="2bef9-107">描述</span><span class="sxs-lookup"><span data-stu-id="2bef9-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="2bef9-108">参数的方差仅适用于接口和委托的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="2bef9-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="2bef9-109">指示缺少变化。</span><span class="sxs-lookup"><span data-stu-id="2bef9-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="2bef9-110">指示协方差。</span><span class="sxs-lookup"><span data-stu-id="2bef9-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="2bef9-111">指示逆变。</span><span class="sxs-lookup"><span data-stu-id="2bef9-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="2bef9-112">特殊约束可应用于任何<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="2bef9-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="2bef9-113">指示没有约束应用于<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="2bef9-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="2bef9-114">指示<xref:System.Type>参数必须是引用类型。</span><span class="sxs-lookup"><span data-stu-id="2bef9-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="2bef9-115">指示<xref:System.Type>参数必须是值类型，不能为 null 的值。</span><span class="sxs-lookup"><span data-stu-id="2bef9-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="2bef9-116">指示<xref:System.Type>参数必须具有默认公共构造函数不采用参数。</span><span class="sxs-lookup"><span data-stu-id="2bef9-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bef9-117">要求</span><span class="sxs-lookup"><span data-stu-id="2bef9-117">Requirements</span></span>  
 <span data-ttu-id="2bef9-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bef9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bef9-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2bef9-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2bef9-120">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bef9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bef9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bef9-121">See Also</span></span>  
 [<span data-ttu-id="2bef9-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2bef9-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
