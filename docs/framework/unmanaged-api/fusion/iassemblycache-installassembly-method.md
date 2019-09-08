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
# <a name="iassemblycacheinstallassembly-method"></a>IAssemblyCache::InstallAssembly 方法
在全局程序集缓存中安装指定的程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwFlags`  
 中在合成 .idl 中定义的标志。 支持以下值：  
  
- IASSEMBLYCACHE_INSTALL_FLAG_REFRESH （0x00000001）  
  
- IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH （0x00000002）  
  
 `pszManifestFilePath`  
 中要安装的程序集的清单的路径。  
  
 `pRefData`  
 中包含安装数据的[FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md)结构。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyCache 接口](iassemblycache-interface.md)
