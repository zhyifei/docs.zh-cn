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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176040"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="426b2-102">IMetaDataAssemblyEmit::SetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="426b2-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="426b2-103">修改指定的 `AssemblyRef` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="426b2-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="426b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="426b2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="426b2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="426b2-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="426b2-106">[在]指定要修改的`AssemblyRef`元数据结构的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="426b2-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="426b2-107">[在]引用程序集的发布者的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="426b2-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="426b2-108">[在]的大小（以字节为单位）。 `pbPublicKeyOrToken`</span><span class="sxs-lookup"><span data-stu-id="426b2-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="426b2-109">[在]程序集的人类可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="426b2-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="426b2-110">[在]指向 ASSEMBLYMETADATA 实例的指针，其中包含程序集的版本、平台和区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="426b2-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="426b2-111">[在]指向与程序集关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="426b2-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="426b2-112">[在]的大小（以字节为单位）。 `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="426b2-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="426b2-113">[在]指定引用程序集属性的[程序集 RefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)值的位组合。</span><span class="sxs-lookup"><span data-stu-id="426b2-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="426b2-114">备注</span><span class="sxs-lookup"><span data-stu-id="426b2-114">Remarks</span></span>  
 <span data-ttu-id="426b2-115">要创建`AssemblyRef`元数据结构，请使用[IMetaDataAssemblyEmit：:DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="426b2-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="426b2-116">要求</span><span class="sxs-lookup"><span data-stu-id="426b2-116">Requirements</span></span>  
 <span data-ttu-id="426b2-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="426b2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="426b2-118">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="426b2-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="426b2-119">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="426b2-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="426b2-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="426b2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426b2-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="426b2-121">See also</span></span>

- [<span data-ttu-id="426b2-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="426b2-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
