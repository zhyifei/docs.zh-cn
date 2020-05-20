---
title: GetRealProcAddress 函数
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 6bbf8366054c58543444a4b710a687198f365e6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617186"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="1511b-102">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="1511b-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="1511b-103">获取从最新安装的公共语言运行时（CLR）版本导出的指定函数的地址。</span><span class="sxs-lookup"><span data-stu-id="1511b-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="1511b-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="1511b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1511b-105">语法</span><span class="sxs-lookup"><span data-stu-id="1511b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1511b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1511b-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="1511b-107">中函数的名称。</span><span class="sxs-lookup"><span data-stu-id="1511b-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1511b-108">弄接收指向函数地址的指针的位置。</span><span class="sxs-lookup"><span data-stu-id="1511b-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1511b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1511b-109">Return Value</span></span>  
 <span data-ttu-id="1511b-110">除了在 CorError 中定义的以下值，此方法还返回 Winerror.h 中定义的标准组件对象模型（COM）错误代码。</span><span class="sxs-lookup"><span data-stu-id="1511b-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="1511b-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="1511b-111">Return code</span></span>|<span data-ttu-id="1511b-112">说明</span><span class="sxs-lookup"><span data-stu-id="1511b-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1511b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1511b-113">S_OK</span></span>|<span data-ttu-id="1511b-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1511b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1511b-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1511b-115">E_POINTER</span></span>|<span data-ttu-id="1511b-116">`ppv` 无效。</span><span class="sxs-lookup"><span data-stu-id="1511b-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="1511b-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="1511b-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="1511b-118">不从运行时导出函数。</span><span class="sxs-lookup"><span data-stu-id="1511b-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1511b-119">要求</span><span class="sxs-lookup"><span data-stu-id="1511b-119">Requirements</span></span>  
 <span data-ttu-id="1511b-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1511b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1511b-121">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1511b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1511b-122">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1511b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1511b-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1511b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1511b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1511b-124">See also</span></span>

- [<span data-ttu-id="1511b-125">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="1511b-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
