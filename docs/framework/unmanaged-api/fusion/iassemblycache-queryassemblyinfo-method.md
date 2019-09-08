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
ms.openlocfilehash: 08b9fdee1138becd4cd5a933f96021c470aadf1f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796789"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="47eb9-102">IAssemblyCache::QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="47eb9-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="47eb9-103">获取有关指定程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="47eb9-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47eb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="47eb9-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47eb9-105">参数</span><span class="sxs-lookup"><span data-stu-id="47eb9-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="47eb9-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="47eb9-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="47eb9-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="47eb9-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="47eb9-108">QUERYASMINFO_FLAG_VALIDATE （0x00000001）</span><span class="sxs-lookup"><span data-stu-id="47eb9-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="47eb9-109">QUERYASMINFO_FLAG_GETSIZE （0x00000002）</span><span class="sxs-lookup"><span data-stu-id="47eb9-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="47eb9-110">中将为其检索数据的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="47eb9-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="47eb9-111">[in，out]包含有关程序集的数据的[ASSEMBLY_INFO](assembly-info-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="47eb9-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47eb9-112">要求</span><span class="sxs-lookup"><span data-stu-id="47eb9-112">Requirements</span></span>  
 <span data-ttu-id="47eb9-113">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47eb9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47eb9-114">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="47eb9-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="47eb9-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47eb9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47eb9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="47eb9-116">See also</span></span>

- [<span data-ttu-id="47eb9-117">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="47eb9-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
