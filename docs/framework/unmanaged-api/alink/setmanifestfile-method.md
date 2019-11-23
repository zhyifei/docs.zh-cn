---
title: SetManifestFile 方法
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: df97f4c37d8f335ce183685debd7c0933be910ed
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445560"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="b123e-102">SetManifestFile 方法</span><span class="sxs-lookup"><span data-stu-id="b123e-102">SetManifestFile Method</span></span>
<span data-ttu-id="b123e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span><span class="sxs-lookup"><span data-stu-id="b123e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b123e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b123e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b123e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b123e-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="b123e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span><span class="sxs-lookup"><span data-stu-id="b123e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b123e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b123e-107">Return Value</span></span>  
 <span data-ttu-id="b123e-108">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="b123e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b123e-109">备注</span><span class="sxs-lookup"><span data-stu-id="b123e-109">Remarks</span></span>  
 <span data-ttu-id="b123e-110">Call this before asking for the Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="b123e-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="b123e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="b123e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="b123e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span><span class="sxs-lookup"><span data-stu-id="b123e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="b123e-113">This enables one to reset the state of the linker to that of initialization time.</span><span class="sxs-lookup"><span data-stu-id="b123e-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b123e-114">要求</span><span class="sxs-lookup"><span data-stu-id="b123e-114">Requirements</span></span>  
 <span data-ttu-id="b123e-115">Requires aLink.h</span><span class="sxs-lookup"><span data-stu-id="b123e-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b123e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b123e-116">See also</span></span>

- [<span data-ttu-id="b123e-117">IALink3 接口</span><span class="sxs-lookup"><span data-stu-id="b123e-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="b123e-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="b123e-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="b123e-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b123e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b123e-120">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="b123e-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
