---
title: IAssemblyCache::UninstallAssembly 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
ms.openlocfilehash: 539a8edf6d7248235a6e672edc9464679a2eab82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134501"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="9c5d8-102">IAssemblyCache::UninstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="9c5d8-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="9c5d8-103">从全局程序集缓存中卸载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c5d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c5d8-104">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c5d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c5d8-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="9c5d8-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="9c5d8-107">中要卸载的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="9c5d8-108">中包含程序集的安装数据的[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-108">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="9c5d8-109">[out，optional]在合成 .idl 中定义的一个处置值。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="9c5d8-110">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="9c5d8-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="9c5d8-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED （1）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="9c5d8-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE （2）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="9c5d8-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED （3）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="9c5d8-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING （4）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="9c5d8-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES （5）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="9c5d8-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND （6）</span><span class="sxs-lookup"><span data-stu-id="9c5d8-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c5d8-117">要求</span><span class="sxs-lookup"><span data-stu-id="9c5d8-117">Requirements</span></span>  
 <span data-ttu-id="9c5d8-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c5d8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c5d8-119">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="9c5d8-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9c5d8-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c5d8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5d8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c5d8-121">See also</span></span>

- [<span data-ttu-id="9c5d8-122">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="9c5d8-122">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
