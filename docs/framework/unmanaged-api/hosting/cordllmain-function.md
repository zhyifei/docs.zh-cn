---
title: _CorDllMain 函数
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666908"
---
# <a name="cordllmain-function"></a><span data-ttu-id="ca9e4-102">\_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="ca9e4-102">\_CorDllMain Function</span></span>

<span data-ttu-id="ca9e4-103">初始化公共语言运行时 (CLR) 中，查找托管的入口点 DLL 程序集 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca9e4-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca9e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca9e4-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="ca9e4-106">[in]已加载的模块实例句柄。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="ca9e4-107">[in]指示调用 DLL 入口点函数。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="ca9e4-108">此参数可以是下列值之一：DLL\_PROCESS_ATTACH、 DLL\_线程\_附加、 DLL\_线程\_附加或 DLL\_过程\_分离。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="ca9e4-109">有关这些值的说明，请参阅`DllMain`Platform SDK 中的文档。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="ca9e4-110">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca9e4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ca9e4-111">Return Value</span></span>  
 <span data-ttu-id="ca9e4-112">此方法返回`true`成功和`false`如果发生错误。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca9e4-113">备注</span><span class="sxs-lookup"><span data-stu-id="ca9e4-113">Remarks</span></span>  
 <span data-ttu-id="ca9e4-114">DLL 程序集由操作系统加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="ca9e4-115">对于可执行程序集，加载程序将调用[ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="ca9e4-116">操作系统加载程序调用此方法而不考虑 DLL 文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="ca9e4-117">`_CorDllMain`由操作系统加载程序直接调用函数。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="ca9e4-118">有关其他信息，请参阅中的备注部分[ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9e4-119">要求</span><span class="sxs-lookup"><span data-stu-id="ca9e4-119">Requirements</span></span>  

 <span data-ttu-id="ca9e4-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca9e4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9e4-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca9e4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca9e4-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ca9e4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca9e4-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9e4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9e4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca9e4-124">See also</span></span>

- [<span data-ttu-id="ca9e4-125">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="ca9e4-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
