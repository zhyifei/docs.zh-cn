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
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045782"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="73995-102">CorGenericParamAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="73995-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="73995-103">包含值，用于描述<xref:System.Type>泛型类型，作为调用中使用参数[IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)。</span><span class="sxs-lookup"><span data-stu-id="73995-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73995-104">语法</span><span class="sxs-lookup"><span data-stu-id="73995-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="73995-105">成员</span><span class="sxs-lookup"><span data-stu-id="73995-105">Members</span></span>  
  
|<span data-ttu-id="73995-106">成员</span><span class="sxs-lookup"><span data-stu-id="73995-106">Member</span></span>|<span data-ttu-id="73995-107">描述</span><span class="sxs-lookup"><span data-stu-id="73995-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="73995-108">参数的变体仅应用于接口和委托的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="73995-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="73995-109">表示不存在的方差。</span><span class="sxs-lookup"><span data-stu-id="73995-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="73995-110">指示协方差。</span><span class="sxs-lookup"><span data-stu-id="73995-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="73995-111">指示逆变。</span><span class="sxs-lookup"><span data-stu-id="73995-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="73995-112">可以将特殊约束应用于任何<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="73995-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="73995-113">指示没有约束应用于<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="73995-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="73995-114">指示<xref:System.Type>参数必须是引用类型。</span><span class="sxs-lookup"><span data-stu-id="73995-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="73995-115">指示<xref:System.Type>参数必须是值类型，不能为 null 值。</span><span class="sxs-lookup"><span data-stu-id="73995-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="73995-116">指示<xref:System.Type>参数必须具有不带参数的默认公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="73995-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73995-117">要求</span><span class="sxs-lookup"><span data-stu-id="73995-117">Requirements</span></span>  
 <span data-ttu-id="73995-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73995-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73995-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="73995-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="73995-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73995-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73995-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="73995-121">See also</span></span>

- [<span data-ttu-id="73995-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="73995-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
