---
title: "IAssemblyCache::QueryAssemblyInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.QueryAssemblyInfo
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 567ff7fc5b9038c4af9aa04e3a07d9585adf44fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="5524d-102">IAssemblyCache::QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5524d-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="5524d-103">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="5524d-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5524d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5524d-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5524d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5524d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="5524d-106">[in]在包括中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="5524d-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="5524d-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="5524d-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="5524d-108">QUERYASMINFO_FLAG_VALIDATE (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="5524d-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="5524d-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="5524d-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="5524d-110">[in]将为其检索数据的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="5524d-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="5524d-111">[在中，out][ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md)结构，其中包含有关程序集的数据。</span><span class="sxs-lookup"><span data-stu-id="5524d-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5524d-112">要求</span><span class="sxs-lookup"><span data-stu-id="5524d-112">Requirements</span></span>  
 <span data-ttu-id="5524d-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5524d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5524d-114">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5524d-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5524d-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5524d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5524d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5524d-116">See Also</span></span>  
 [<span data-ttu-id="5524d-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="5524d-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
