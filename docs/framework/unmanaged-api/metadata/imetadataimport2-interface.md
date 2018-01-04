---
title: "IMetaDataImport2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7cd9d2cd2837ff43fbb266717546db3aa98190e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="2c3fe-102">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="2c3fe-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="2c3fe-103">扩展[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口，以提供使用泛型类型的功能。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c3fe-104">方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-104">Methods</span></span>  
  
|<span data-ttu-id="2c3fe-105">方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-105">Method</span></span>|<span data-ttu-id="2c3fe-106">描述</span><span class="sxs-lookup"><span data-stu-id="2c3fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c3fe-107">EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="2c3fe-108">获取与指定标记所表示的泛型参数相关联的泛型参数约束的数组的枚举数。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="2c3fe-109">EnumGenericParams 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="2c3fe-110">获取与指定的 TypeDef 或 MethodDef 相关联的泛型参数标记为数组的枚举器令牌。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="2c3fe-111">EnumMethodSpecs 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="2c3fe-112">获取的枚举数数组 MethodSpec 与关联的标记指定的 MethodDef 或 MemberRef 令牌。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="2c3fe-113">GetGenericParamConstraintProps 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="2c3fe-114">获取具有指定的约束标记所表示的泛型参数约束关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="2c3fe-115">GetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="2c3fe-116">获取与指定标记所表示的泛型参数关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="2c3fe-117">GetMethodSpecProps 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="2c3fe-118">获取由指定 MethodSpec 所引用的方法的元数据签名令牌。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="2c3fe-119">GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="2c3fe-120">获取一个值，标识可移植可执行 (PE) 中的代码的性质文件，通常是 DLL 或 EXE 文件，在当前元数据范围内定义</span><span class="sxs-lookup"><span data-stu-id="2c3fe-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="2c3fe-121">GetVersionString 方法</span><span class="sxs-lookup"><span data-stu-id="2c3fe-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="2c3fe-122">获取用于生成程序集的运行时的版本号。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c3fe-123">惠?</span><span class="sxs-lookup"><span data-stu-id="2c3fe-123">Requirements</span></span>  
 <span data-ttu-id="2c3fe-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c3fe-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c3fe-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c3fe-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c3fe-126">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c3fe-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c3fe-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c3fe-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3fe-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c3fe-128">See Also</span></span>  
 <xref:System.Reflection.PortableExecutableKinds>  
 [<span data-ttu-id="2c3fe-129">元数据接口</span><span class="sxs-lookup"><span data-stu-id="2c3fe-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="2c3fe-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="2c3fe-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
