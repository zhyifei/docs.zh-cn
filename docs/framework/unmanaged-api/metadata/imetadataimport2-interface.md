---
title: IMetaDataImport2 接口
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429206"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="14c26-102">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="14c26-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="14c26-103">扩展[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口以提供使用泛型类型的功能。</span><span class="sxs-lookup"><span data-stu-id="14c26-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14c26-104">方法</span><span class="sxs-lookup"><span data-stu-id="14c26-104">Methods</span></span>  
  
|<span data-ttu-id="14c26-105">方法</span><span class="sxs-lookup"><span data-stu-id="14c26-105">Method</span></span>|<span data-ttu-id="14c26-106">说明</span><span class="sxs-lookup"><span data-stu-id="14c26-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14c26-107">EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="14c26-108">获取与指定标记表示的泛型参数关联的泛型参数约束数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="14c26-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="14c26-109">EnumGenericParams 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="14c26-110">获取与指定的 TypeDef 或 MethodDef 标记相关联的泛型参数标记数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="14c26-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="14c26-111">EnumMethodSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="14c26-112">获取与指定的 MethodDef 或 MemberRef 标记相关联的 MethodSpec 标记数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="14c26-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="14c26-113">GetGenericParamConstraintProps 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="14c26-114">获取与指定约束标记所表示的泛型参数约束关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="14c26-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="14c26-115">GetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="14c26-116">获取与指定标记表示的泛型参数关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="14c26-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="14c26-117">GetMethodSpecProps 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="14c26-118">获取指定的 MethodSpec 标记所引用的方法的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="14c26-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="14c26-119">GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="14c26-120">获取一个值，该值标识可移植可执行（PE）文件中代码的性质，通常是在当前元数据范围内定义的 DLL 或 EXE 文件</span><span class="sxs-lookup"><span data-stu-id="14c26-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="14c26-121">GetVersionString 方法</span><span class="sxs-lookup"><span data-stu-id="14c26-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="14c26-122">获取用于生成程序集的运行时的版本号。</span><span class="sxs-lookup"><span data-stu-id="14c26-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14c26-123">要求</span><span class="sxs-lookup"><span data-stu-id="14c26-123">Requirements</span></span>  
 <span data-ttu-id="14c26-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14c26-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14c26-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="14c26-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14c26-126">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="14c26-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="14c26-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14c26-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c26-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14c26-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="14c26-129">元数据接口</span><span class="sxs-lookup"><span data-stu-id="14c26-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="14c26-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="14c26-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
