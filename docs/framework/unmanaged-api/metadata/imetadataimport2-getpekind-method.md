---
title: "IMetaDataImport2::GetPEKind 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8dc31877ba3550fa8faf610b831dfd2e7b313ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="a26bf-102">IMetaDataImport2::GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="a26bf-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="a26bf-103">获取一个值，标识可移植可执行 (PE) 中的代码的性质文件，通常是 DLL 或 EXE 文件，在当前元数据范围中定义。</span><span class="sxs-lookup"><span data-stu-id="a26bf-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a26bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="a26bf-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a26bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="a26bf-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="a26bf-106">[out]指向的值的指针[CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)描述 PE 文件的枚举。</span><span class="sxs-lookup"><span data-stu-id="a26bf-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="a26bf-107">[out]指向一个值，标识计算机的体系结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a26bf-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="a26bf-108">请参阅下节，了解可能的值。</span><span class="sxs-lookup"><span data-stu-id="a26bf-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a26bf-109">备注</span><span class="sxs-lookup"><span data-stu-id="a26bf-109">Remarks</span></span>  
 <span data-ttu-id="a26bf-110">由引用的值`pdwMachine`参数可以为以下项之一。</span><span class="sxs-lookup"><span data-stu-id="a26bf-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="a26bf-111">“值”</span><span class="sxs-lookup"><span data-stu-id="a26bf-111">Value</span></span>|<span data-ttu-id="a26bf-112">计算机体系结构</span><span class="sxs-lookup"><span data-stu-id="a26bf-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="a26bf-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="a26bf-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="a26bf-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="a26bf-114">0x014C</span></span>|<span data-ttu-id="a26bf-115">x86</span><span class="sxs-lookup"><span data-stu-id="a26bf-115">x86</span></span>|  
|<span data-ttu-id="a26bf-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="a26bf-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="a26bf-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="a26bf-117">0x0200</span></span>|<span data-ttu-id="a26bf-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="a26bf-118">Intel IPF</span></span>|  
|<span data-ttu-id="a26bf-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="a26bf-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="a26bf-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="a26bf-120">0x8664</span></span>|<span data-ttu-id="a26bf-121">X64</span><span class="sxs-lookup"><span data-stu-id="a26bf-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a26bf-122">惠?</span><span class="sxs-lookup"><span data-stu-id="a26bf-122">Requirements</span></span>  
 <span data-ttu-id="a26bf-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a26bf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a26bf-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a26bf-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a26bf-125">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a26bf-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a26bf-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a26bf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a26bf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a26bf-127">See Also</span></span>  
 [<span data-ttu-id="a26bf-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a26bf-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="a26bf-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a26bf-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a26bf-130">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="a26bf-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
