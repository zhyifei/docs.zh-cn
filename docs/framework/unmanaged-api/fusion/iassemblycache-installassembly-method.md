---
title: IAssemblyCache::InstallAssembly 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7199fbc0c8760354269a50b647952729860c805b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697545"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="5dd21-102">IAssemblyCache::InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="5dd21-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="5dd21-103">将指定的程序集安装在全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="5dd21-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd21-104">语法</span><span class="sxs-lookup"><span data-stu-id="5dd21-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dd21-105">参数</span><span class="sxs-lookup"><span data-stu-id="5dd21-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="5dd21-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="5dd21-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="5dd21-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="5dd21-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="5dd21-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="5dd21-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="5dd21-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="5dd21-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="5dd21-110">[in]要安装的程序集清单的路径。</span><span class="sxs-lookup"><span data-stu-id="5dd21-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="5dd21-111">[in]一个[FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)结构，其中包含安装程序数据。</span><span class="sxs-lookup"><span data-stu-id="5dd21-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd21-112">要求</span><span class="sxs-lookup"><span data-stu-id="5dd21-112">Requirements</span></span>  
 <span data-ttu-id="5dd21-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5dd21-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd21-114">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5dd21-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5dd21-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd21-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dd21-116">See also</span></span>

- [<span data-ttu-id="5dd21-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="5dd21-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
