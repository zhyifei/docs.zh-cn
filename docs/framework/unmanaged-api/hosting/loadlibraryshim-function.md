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
ms.openlocfilehash: 9ab44ce8f51620d83084d1dd16e98b2b310feb76
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968942"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="a54c8-102">LoadLibraryShim 函数</span><span class="sxs-lookup"><span data-stu-id="a54c8-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="a54c8-103">加载 .NET Framework 可再发行组件包中包含的 DLL 的指定版本。</span><span class="sxs-lookup"><span data-stu-id="a54c8-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="a54c8-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="a54c8-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="a54c8-105">改为使用[ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a54c8-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54c8-106">语法</span><span class="sxs-lookup"><span data-stu-id="a54c8-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a54c8-107">参数</span><span class="sxs-lookup"><span data-stu-id="a54c8-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="a54c8-108">中以零结尾的字符串, 表示要从 .NET Framework 库中加载的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="a54c8-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="a54c8-109">中以零结尾的字符串, 表示要加载的 DLL 的版本。</span><span class="sxs-lookup"><span data-stu-id="a54c8-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="a54c8-110">如果`szVersion`为 null, 则为加载选择的版本是指定 DLL 的最新版本, 该版本低于版本4。</span><span class="sxs-lookup"><span data-stu-id="a54c8-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="a54c8-111">也就是说, 如果`szVersion`为 null, 则忽略等于或大于版本4的所有版本, 如果未安装低于版本4的版本, 则 DLL 无法加载。</span><span class="sxs-lookup"><span data-stu-id="a54c8-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="a54c8-112">这是为了确保 .NET Framework 4 的安装不会影响预先存在的应用程序或组件。</span><span class="sxs-lookup"><span data-stu-id="a54c8-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="a54c8-113">请参阅 CLR 团队博客中的 "[进程内 SxS 和迁移快速入门](https://go.microsoft.com/fwlink/?LinkId=200329)条目。</span><span class="sxs-lookup"><span data-stu-id="a54c8-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a54c8-114">留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="a54c8-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="a54c8-115">弄指向模块的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="a54c8-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a54c8-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a54c8-116">Return Value</span></span>  
 <span data-ttu-id="a54c8-117">除以下值外, 此方法还返回 Winerror.h 中定义的标准组件对象模型 (COM) 错误代码。</span><span class="sxs-lookup"><span data-stu-id="a54c8-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a54c8-118">返回代码</span><span class="sxs-lookup"><span data-stu-id="a54c8-118">Return code</span></span>|<span data-ttu-id="a54c8-119">描述</span><span class="sxs-lookup"><span data-stu-id="a54c8-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a54c8-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="a54c8-120">S_OK</span></span>|<span data-ttu-id="a54c8-121">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="a54c8-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="a54c8-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="a54c8-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="a54c8-123">加载`szDllName`需要加载公共语言运行时 (clr), 并且无法加载 CLR 的必要版本。</span><span class="sxs-lookup"><span data-stu-id="a54c8-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a54c8-124">备注</span><span class="sxs-lookup"><span data-stu-id="a54c8-124">Remarks</span></span>  
 <span data-ttu-id="a54c8-125">此函数用于加载 .NET Framework 可再发行组件包中包含的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a54c8-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="a54c8-126">它不会加载用户生成的 Dll。</span><span class="sxs-lookup"><span data-stu-id="a54c8-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a54c8-127">从 .NET Framework 版本2.0 开始, 加载合成 .dll 会导致加载 CLR。</span><span class="sxs-lookup"><span data-stu-id="a54c8-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="a54c8-128">这是因为, 合成 .dll 中的函数现在是由运行时提供其实现的包装器。</span><span class="sxs-lookup"><span data-stu-id="a54c8-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a54c8-129">要求</span><span class="sxs-lookup"><span data-stu-id="a54c8-129">Requirements</span></span>  
 <span data-ttu-id="a54c8-130">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a54c8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a54c8-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a54c8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a54c8-132">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a54c8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a54c8-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="a54c8-133">See also</span></span>

- [<span data-ttu-id="a54c8-134">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="a54c8-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
