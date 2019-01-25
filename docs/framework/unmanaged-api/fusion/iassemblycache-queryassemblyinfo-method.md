---
title: IAssemblyCache::QueryAssemblyInfo 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1c3d20b1b9470c744f6dca9ef638555b9322c1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658112"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="e2707-102">IAssemblyCache::QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="e2707-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="e2707-103">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="e2707-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2707-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2707-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2707-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2707-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e2707-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="e2707-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="e2707-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e2707-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e2707-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="e2707-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="e2707-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="e2707-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="e2707-110">[in]将为其检索数据的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="e2707-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="e2707-111">[in、 out][ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md)结构，其中包含有关程序集的数据。</span><span class="sxs-lookup"><span data-stu-id="e2707-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2707-112">要求</span><span class="sxs-lookup"><span data-stu-id="e2707-112">Requirements</span></span>  
 <span data-ttu-id="e2707-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2707-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2707-114">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e2707-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e2707-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2707-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2707-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2707-116">See also</span></span>
- [<span data-ttu-id="e2707-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="e2707-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
