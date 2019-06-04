---
title: LoadLibraryShim 函数
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87ca5470fe5994d34d12a339c2d92a5f3917063d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490222"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="aff14-102">LoadLibraryShim 函数</span><span class="sxs-lookup"><span data-stu-id="aff14-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="aff14-103">加载指定的版本的.NET Framework 可再发行组件包中包含的 DLL。</span><span class="sxs-lookup"><span data-stu-id="aff14-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="aff14-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="aff14-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="aff14-105">使用[iclrruntimeinfo:: Loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="aff14-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff14-106">语法</span><span class="sxs-lookup"><span data-stu-id="aff14-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aff14-107">参数</span><span class="sxs-lookup"><span data-stu-id="aff14-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="aff14-108">[in]的以零结尾的字符串表示要从.NET Framework 库加载的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="aff14-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="aff14-109">[in]的以零结尾的字符串表示要加载的 dll 版本。</span><span class="sxs-lookup"><span data-stu-id="aff14-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="aff14-110">如果`szVersion`是 null，选择用于加载是指定早于版本 4 的 DLL 的最新版本的版本。</span><span class="sxs-lookup"><span data-stu-id="aff14-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="aff14-111">如果所有版本等于或大于版本 4 则将都忽略，即`szVersion`为 null，并且如果不安装任何版本低于版本 4，则无法加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="aff14-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="aff14-112">这是为了确保安装的.NET Framework 4 不影响现有应用程序或组件。</span><span class="sxs-lookup"><span data-stu-id="aff14-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="aff14-113">请参阅文章[进程内并行和迁移快速启动](https://go.microsoft.com/fwlink/?LinkId=200329)CLR 团队博客中。</span><span class="sxs-lookup"><span data-stu-id="aff14-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="aff14-114">留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="aff14-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="aff14-115">[out]指向模块的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="aff14-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aff14-116">返回值</span><span class="sxs-lookup"><span data-stu-id="aff14-116">Return Value</span></span>  
 <span data-ttu-id="aff14-117">此方法返回标准的组件对象模型 (COM) 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="aff14-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="aff14-118">返回代码</span><span class="sxs-lookup"><span data-stu-id="aff14-118">Return code</span></span>|<span data-ttu-id="aff14-119">描述</span><span class="sxs-lookup"><span data-stu-id="aff14-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="aff14-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="aff14-120">S_OK</span></span>|<span data-ttu-id="aff14-121">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="aff14-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="aff14-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="aff14-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="aff14-123">正在加载`szDllName`需要在加载公共语言运行时 (CLR)，并在 CLR 的必要版本无法加载。</span><span class="sxs-lookup"><span data-stu-id="aff14-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aff14-124">备注</span><span class="sxs-lookup"><span data-stu-id="aff14-124">Remarks</span></span>  
 <span data-ttu-id="aff14-125">此函数用于加载.NET Framework 可再发行组件包中包含的 Dll。</span><span class="sxs-lookup"><span data-stu-id="aff14-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="aff14-126">它将不加载用户生成的 Dll。</span><span class="sxs-lookup"><span data-stu-id="aff14-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff14-127">从.NET Framework 2.0 版开始，将加载 Fusion.dll 导致要加载的 CLR。</span><span class="sxs-lookup"><span data-stu-id="aff14-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="aff14-128">这是因为在 Fusion.dll 函数现在是由运行时提供其实现的包装器。</span><span class="sxs-lookup"><span data-stu-id="aff14-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aff14-129">要求</span><span class="sxs-lookup"><span data-stu-id="aff14-129">Requirements</span></span>  
 <span data-ttu-id="aff14-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aff14-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aff14-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aff14-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aff14-132">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aff14-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff14-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff14-133">See also</span></span>

- [<span data-ttu-id="aff14-134">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="aff14-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
