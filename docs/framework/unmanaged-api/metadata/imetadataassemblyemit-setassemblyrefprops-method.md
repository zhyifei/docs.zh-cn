---
title: IMetaDataAssemblyEmit::SetAssemblyRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a4f0fd100397fc52ca917c54f0276598d714640
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642839"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="84bd0-102">IMetaDataAssemblyEmit::SetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="84bd0-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="84bd0-103">修改指定的 `AssemblyRef` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="84bd0-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84bd0-104">语法</span><span class="sxs-lookup"><span data-stu-id="84bd0-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84bd0-105">参数</span><span class="sxs-lookup"><span data-stu-id="84bd0-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="84bd0-106">[in]指定的元数据标记`AssemblyRef`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="84bd0-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="84bd0-107">[in]引用的程序集的发布服务器的公钥。</span><span class="sxs-lookup"><span data-stu-id="84bd0-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="84bd0-108">[in]以字节为单位的大小`pbPublicKeyOrToken`。</span><span class="sxs-lookup"><span data-stu-id="84bd0-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="84bd0-109">[in]用户可读文本的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="84bd0-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="84bd0-110">[in]指向包含程序集的版本、 平台和区域设置信息的 ASSEMBLYMETADATA 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="84bd0-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="84bd0-111">[in]指向与该程序集关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="84bd0-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="84bd0-112">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="84bd0-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="84bd0-113">[in]按位组合[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)指定引用程序集的属性的值。</span><span class="sxs-lookup"><span data-stu-id="84bd0-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84bd0-114">备注</span><span class="sxs-lookup"><span data-stu-id="84bd0-114">Remarks</span></span>  
 <span data-ttu-id="84bd0-115">若要创建`AssemblyRef`元数据结构，使用[imetadataassemblyemit:: Defineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="84bd0-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84bd0-116">要求</span><span class="sxs-lookup"><span data-stu-id="84bd0-116">Requirements</span></span>  
 <span data-ttu-id="84bd0-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84bd0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84bd0-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84bd0-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84bd0-119">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="84bd0-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84bd0-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84bd0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84bd0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="84bd0-121">See also</span></span>
- [<span data-ttu-id="84bd0-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="84bd0-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
