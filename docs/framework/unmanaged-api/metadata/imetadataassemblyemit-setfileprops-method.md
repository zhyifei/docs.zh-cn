---
title: IMetaDataAssemblyEmit::SetFileProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431873"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="ab813-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="ab813-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="ab813-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="ab813-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab813-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab813-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab813-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab813-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="ab813-106">中用于指定要修改的 `File` 元数据结构的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ab813-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="ab813-107">中指向与该文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="ab813-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="ab813-108">中`pbHashValue`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab813-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="ab813-109">中[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值的按位组合，用于指定文件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="ab813-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab813-110">备注</span><span class="sxs-lookup"><span data-stu-id="ab813-110">Remarks</span></span>  
 <span data-ttu-id="ab813-111">若要创建 `File` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ab813-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab813-112">要求</span><span class="sxs-lookup"><span data-stu-id="ab813-112">Requirements</span></span>  
 <span data-ttu-id="ab813-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab813-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab813-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ab813-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab813-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab813-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab813-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab813-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab813-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab813-117">See also</span></span>

- [<span data-ttu-id="ab813-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="ab813-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
