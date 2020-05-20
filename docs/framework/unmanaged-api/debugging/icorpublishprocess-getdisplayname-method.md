---
title: ICorPublishProcess::GetDisplayName 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: dc76274d3b0acbbe0b03eb141d2b3e6ff9063afb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421119"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="d1e00-102">ICorPublishProcess::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="d1e00-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="d1e00-103">获取此[ICorPublishProcess](icorpublishprocess-interface.md)引用的进程的可执行文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="d1e00-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e00-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1e00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e00-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1e00-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d1e00-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="d1e00-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d1e00-107">弄在数组中返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="d1e00-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="d1e00-108">弄用于存储可执行文件的名称（包括完整路径）的数组。</span><span class="sxs-lookup"><span data-stu-id="d1e00-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="d1e00-109">名称以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="d1e00-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e00-110">要求</span><span class="sxs-lookup"><span data-stu-id="d1e00-110">Requirements</span></span>  
 <span data-ttu-id="d1e00-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1e00-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e00-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="d1e00-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d1e00-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1e00-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1e00-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e00-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e00-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1e00-115">See also</span></span>

- [<span data-ttu-id="d1e00-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="d1e00-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
