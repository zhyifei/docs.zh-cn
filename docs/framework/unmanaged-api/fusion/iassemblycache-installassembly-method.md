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
ms.openlocfilehash: 95c65e73c118b5358ac0a92dd0a1ca5545558e73
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796799"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="5be46-102">IAssemblyCache::InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="5be46-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="5be46-103">在全局程序集缓存中安装指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="5be46-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be46-104">语法</span><span class="sxs-lookup"><span data-stu-id="5be46-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5be46-105">参数</span><span class="sxs-lookup"><span data-stu-id="5be46-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="5be46-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="5be46-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="5be46-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="5be46-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="5be46-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH （0x00000001）</span><span class="sxs-lookup"><span data-stu-id="5be46-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="5be46-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH （0x00000002）</span><span class="sxs-lookup"><span data-stu-id="5be46-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="5be46-110">中要安装的程序集的清单的路径。</span><span class="sxs-lookup"><span data-stu-id="5be46-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="5be46-111">中包含安装数据的[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5be46-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5be46-112">要求</span><span class="sxs-lookup"><span data-stu-id="5be46-112">Requirements</span></span>  
 <span data-ttu-id="5be46-113">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5be46-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5be46-114">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="5be46-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5be46-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5be46-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be46-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5be46-116">See also</span></span>

- [<span data-ttu-id="5be46-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="5be46-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
