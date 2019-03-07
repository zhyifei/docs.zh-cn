---
title: IMetaDataImport2::GetPEKind 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3d0ee533ec0ece308f87c170846ef102bd3a3b9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478849"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="eca19-102">IMetaDataImport2::GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="eca19-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="eca19-103">获取一个值，标识的性质可移植可执行 (PE) 中的代码文件，通常是 DLL 或 EXE 文件，在当前元数据范围中定义。</span><span class="sxs-lookup"><span data-stu-id="eca19-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca19-104">语法</span><span class="sxs-lookup"><span data-stu-id="eca19-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eca19-105">参数</span><span class="sxs-lookup"><span data-stu-id="eca19-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="eca19-106">[out]指向的值的指针[CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)描述 PE 文件的枚举。</span><span class="sxs-lookup"><span data-stu-id="eca19-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="eca19-107">[out]指向一个值，标识计算机体系结构的指针。</span><span class="sxs-lookup"><span data-stu-id="eca19-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="eca19-108">请参阅下节，了解可能的值。</span><span class="sxs-lookup"><span data-stu-id="eca19-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eca19-109">备注</span><span class="sxs-lookup"><span data-stu-id="eca19-109">Remarks</span></span>  
 <span data-ttu-id="eca19-110">由引用的值`pdwMachine`参数可以是以下值之一。</span><span class="sxs-lookup"><span data-stu-id="eca19-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="eca19-111">值</span><span class="sxs-lookup"><span data-stu-id="eca19-111">Value</span></span>|<span data-ttu-id="eca19-112">计算机体系结构</span><span class="sxs-lookup"><span data-stu-id="eca19-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="eca19-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="eca19-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="eca19-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="eca19-114">0x014C</span></span>|<span data-ttu-id="eca19-115">x86</span><span class="sxs-lookup"><span data-stu-id="eca19-115">x86</span></span>|  
|<span data-ttu-id="eca19-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="eca19-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="eca19-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="eca19-117">0x0200</span></span>|<span data-ttu-id="eca19-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="eca19-118">Intel IPF</span></span>|  
|<span data-ttu-id="eca19-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="eca19-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="eca19-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="eca19-120">0x8664</span></span>|<span data-ttu-id="eca19-121">X64</span><span class="sxs-lookup"><span data-stu-id="eca19-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eca19-122">要求</span><span class="sxs-lookup"><span data-stu-id="eca19-122">Requirements</span></span>  
 <span data-ttu-id="eca19-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eca19-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eca19-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eca19-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eca19-125">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eca19-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eca19-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eca19-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca19-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="eca19-127">See also</span></span>
- [<span data-ttu-id="eca19-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="eca19-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="eca19-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="eca19-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eca19-130">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="eca19-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
