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
ms.openlocfilehash: ec08c786992996ec6f44038ff3c1596cada88484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127074"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="e2acf-102">IAssemblyCache::InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="e2acf-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="e2acf-103">在全局程序集缓存中安装指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="e2acf-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2acf-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2acf-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2acf-105">参数</span><span class="sxs-lookup"><span data-stu-id="e2acf-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e2acf-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="e2acf-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="e2acf-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e2acf-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="e2acf-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH （0x00000001）</span><span class="sxs-lookup"><span data-stu-id="e2acf-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="e2acf-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH （0x00000002）</span><span class="sxs-lookup"><span data-stu-id="e2acf-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="e2acf-110">中要安装的程序集的清单的路径。</span><span class="sxs-lookup"><span data-stu-id="e2acf-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="e2acf-111">中包含安装数据的[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e2acf-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2acf-112">要求</span><span class="sxs-lookup"><span data-stu-id="e2acf-112">Requirements</span></span>  
 <span data-ttu-id="e2acf-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2acf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2acf-114">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="e2acf-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e2acf-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2acf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2acf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2acf-116">See also</span></span>

- [<span data-ttu-id="e2acf-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="e2acf-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
