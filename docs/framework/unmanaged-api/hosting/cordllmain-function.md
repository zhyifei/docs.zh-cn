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
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616601"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="4efd4-102">\_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="4efd4-102">\_CorDllMain Function</span></span>

<span data-ttu-id="4efd4-103">初始化公共语言运行时（CLR），定位 DLL 程序集的 CLR 头中的托管入口点，然后开始执行。</span><span class="sxs-lookup"><span data-stu-id="4efd4-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4efd4-104">语法</span><span class="sxs-lookup"><span data-stu-id="4efd4-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4efd4-105">参数</span><span class="sxs-lookup"><span data-stu-id="4efd4-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="4efd4-106">中加载的模块的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="4efd4-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="4efd4-107">中指示调用 DLL 入口点函数的原因。</span><span class="sxs-lookup"><span data-stu-id="4efd4-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="4efd4-108">此参数可以是下列值之一： DLL \_ PROCESS_ATTACH、dll \_ 线程 \_ 附加、dll \_ 线程 \_ 附加或 dll \_ 进程 \_ 分离。</span><span class="sxs-lookup"><span data-stu-id="4efd4-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="4efd4-109">有关这些值的说明，请参阅 `DllMain` PLATFORM SDK 中的文档。</span><span class="sxs-lookup"><span data-stu-id="4efd4-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="4efd4-110">中用.</span><span class="sxs-lookup"><span data-stu-id="4efd4-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4efd4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4efd4-111">Return Value</span></span>  
 <span data-ttu-id="4efd4-112">`true`如果发生错误，则此方法将返回成功 `false` 。</span><span class="sxs-lookup"><span data-stu-id="4efd4-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4efd4-113">备注</span><span class="sxs-lookup"><span data-stu-id="4efd4-113">Remarks</span></span>  
 <span data-ttu-id="4efd4-114">此函数由 DLL 程序集的操作系统加载程序调用。</span><span class="sxs-lookup"><span data-stu-id="4efd4-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="4efd4-115">对于可执行程序集，加载程序将调用[ \_ CorExeMain](corexemain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="4efd4-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="4efd4-116">操作系统加载程序将调用此方法，而不考虑 DLL 文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="4efd4-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="4efd4-117">`_CorDllMain`函数由操作系统加载程序直接调用。</span><span class="sxs-lookup"><span data-stu-id="4efd4-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="4efd4-118">有关其他信息，请参阅[ \_ CorValidateImage](corvalidateimage-function.md)主题中的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="4efd4-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4efd4-119">要求</span><span class="sxs-lookup"><span data-stu-id="4efd4-119">Requirements</span></span>  

 <span data-ttu-id="4efd4-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4efd4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4efd4-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4efd4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4efd4-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4efd4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4efd4-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4efd4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efd4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4efd4-124">See also</span></span>

- [<span data-ttu-id="4efd4-125">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="4efd4-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
