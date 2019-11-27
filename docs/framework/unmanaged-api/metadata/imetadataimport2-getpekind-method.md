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
ms.openlocfilehash: 0464c61e4ff01483e10fb5708d5ed4b5f5ed63d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445232"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="4f71d-102">IMetaDataImport2::GetPEKind 方法</span><span class="sxs-lookup"><span data-stu-id="4f71d-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="4f71d-103">获取一个值，该值标识可移植可执行（PE）文件中代码的性质（通常为 DLL 或 EXE 文件），该文件在当前的元数据范围内定义。</span><span class="sxs-lookup"><span data-stu-id="4f71d-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f71d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f71d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f71d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f71d-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="4f71d-106">弄一个指针，指向描述 PE 文件的[CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="4f71d-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="4f71d-107">弄一个指针，指向用于标识计算机体系结构的值。</span><span class="sxs-lookup"><span data-stu-id="4f71d-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="4f71d-108">有关可能的值，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="4f71d-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f71d-109">备注</span><span class="sxs-lookup"><span data-stu-id="4f71d-109">Remarks</span></span>  
 <span data-ttu-id="4f71d-110">`pdwMachine` 参数引用的值可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="4f71d-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="4f71d-111">值</span><span class="sxs-lookup"><span data-stu-id="4f71d-111">Value</span></span>|<span data-ttu-id="4f71d-112">计算机体系结构</span><span class="sxs-lookup"><span data-stu-id="4f71d-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="4f71d-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="4f71d-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="4f71d-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="4f71d-114">0x014C</span></span>|<span data-ttu-id="4f71d-115">x86</span><span class="sxs-lookup"><span data-stu-id="4f71d-115">x86</span></span>|  
|<span data-ttu-id="4f71d-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="4f71d-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="4f71d-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="4f71d-117">0x0200</span></span>|<span data-ttu-id="4f71d-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="4f71d-118">Intel IPF</span></span>|  
|<span data-ttu-id="4f71d-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="4f71d-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="4f71d-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="4f71d-120">0x8664</span></span>|<span data-ttu-id="4f71d-121">x64</span><span class="sxs-lookup"><span data-stu-id="4f71d-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f71d-122">要求</span><span class="sxs-lookup"><span data-stu-id="4f71d-122">Requirements</span></span>  
 <span data-ttu-id="4f71d-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f71d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f71d-124">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4f71d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f71d-125">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4f71d-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f71d-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f71d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f71d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f71d-127">See also</span></span>

- [<span data-ttu-id="4f71d-128">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4f71d-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="4f71d-129">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4f71d-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4f71d-130">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="4f71d-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)
