---
title: GetTypeLibInfo 函数
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="feb5c-102">GetTypeLibInfo 函数</span><span class="sxs-lookup"><span data-stu-id="feb5c-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="feb5c-103">返回有关指定的类型库的信息通过检查其[TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="feb5c-103">Returns information about the specified type library by examining its [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb5c-104">语法</span><span class="sxs-lookup"><span data-stu-id="feb5c-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="feb5c-105">参数</span><span class="sxs-lookup"><span data-stu-id="feb5c-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="feb5c-106">[in]类型库的文件名称。</span><span class="sxs-lookup"><span data-stu-id="feb5c-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="feb5c-107">[out]类型库的 GUID。</span><span class="sxs-lookup"><span data-stu-id="feb5c-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="feb5c-108">[out]类型库的本地化 ID。</span><span class="sxs-lookup"><span data-stu-id="feb5c-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="feb5c-109">[out]A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx)标识目标操作系统为类型库的标志。</span><span class="sxs-lookup"><span data-stu-id="feb5c-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="feb5c-110">常见的值为 SYS_WIN32 和 SYS_WIN64。</span><span class="sxs-lookup"><span data-stu-id="feb5c-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="feb5c-111">[out]主版本号，类型库。</span><span class="sxs-lookup"><span data-stu-id="feb5c-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="feb5c-112">例如，对于版本*x.y*，主版本号是*x*。</span><span class="sxs-lookup"><span data-stu-id="feb5c-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="feb5c-113">[out]类型库次版本号。</span><span class="sxs-lookup"><span data-stu-id="feb5c-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="feb5c-114">例如，对于版本*x.y*，次版本号是*y*。</span><span class="sxs-lookup"><span data-stu-id="feb5c-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feb5c-115">备注</span><span class="sxs-lookup"><span data-stu-id="feb5c-115">Remarks</span></span>  
 <span data-ttu-id="feb5c-116">`GetTypeLibInfo`函数调用[Tlbexp.exe （类型库导出程序）](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)。</span><span class="sxs-lookup"><span data-stu-id="feb5c-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="feb5c-117">此工具会生成类型库描述公共语言运行时 (CLR) 程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="feb5c-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="feb5c-118">如果任何参数为 null，则该函数将返回`HRESULT`的`E_POINTER`。</span><span class="sxs-lookup"><span data-stu-id="feb5c-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="feb5c-119">否则，它将返回 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="feb5c-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb5c-120">要求</span><span class="sxs-lookup"><span data-stu-id="feb5c-120">Requirements</span></span>  
 <span data-ttu-id="feb5c-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="feb5c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb5c-122">**标头：** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="feb5c-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="feb5c-123">**库：** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="feb5c-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="feb5c-124">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb5c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb5c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="feb5c-125">See Also</span></span>  
 [<span data-ttu-id="feb5c-126">Tlbexp Helper 函数</span><span class="sxs-lookup"><span data-stu-id="feb5c-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="feb5c-127">[LoadTypeLibEx 函数](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="feb5c-127">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span></span>
