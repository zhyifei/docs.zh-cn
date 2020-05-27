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
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008061"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="1e57c-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="1e57c-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="1e57c-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="1e57c-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e57c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e57c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e57c-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e57c-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="1e57c-106">中`File`用于指定要修改的元数据结构的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1e57c-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="1e57c-107">中指向与该文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="1e57c-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="1e57c-108">中的大小（以字节为单位） `pbHashValue` 。</span><span class="sxs-lookup"><span data-stu-id="1e57c-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="1e57c-109">中[CorFileFlags](corfileflags-enumeration.md)值的按位组合，用于指定文件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="1e57c-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e57c-110">备注</span><span class="sxs-lookup"><span data-stu-id="1e57c-110">Remarks</span></span>  
 <span data-ttu-id="1e57c-111">若要创建 `File` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efinefile](imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1e57c-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e57c-112">要求</span><span class="sxs-lookup"><span data-stu-id="1e57c-112">Requirements</span></span>  
 <span data-ttu-id="1e57c-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e57c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e57c-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1e57c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e57c-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1e57c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e57c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e57c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e57c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e57c-117">See also</span></span>

- [<span data-ttu-id="1e57c-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1e57c-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
