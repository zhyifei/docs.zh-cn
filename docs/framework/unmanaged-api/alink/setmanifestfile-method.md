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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787212"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="d0ee2-102">SetManifestFile 方法</span><span class="sxs-lookup"><span data-stu-id="d0ee2-102">SetManifestFile Method</span></span>
<span data-ttu-id="d0ee2-103">使您能够在创建程序集时指定或重置链接器使用的清单文件。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0ee2-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0ee2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0ee2-105">参数</span><span class="sxs-lookup"><span data-stu-id="d0ee2-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="d0ee2-106">其内容将放入 Win32 资源 blob 中的清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0ee2-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d0ee2-107">Return Value</span></span>  
 <span data-ttu-id="d0ee2-108">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0ee2-109">备注</span><span class="sxs-lookup"><span data-stu-id="d0ee2-109">Remarks</span></span>  
 <span data-ttu-id="d0ee2-110">在请求 Win32ResBlob 之前调用此。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="d0ee2-111">`pszFile`参数的值是清单文件的名称，其内容被读取并放入 Win32 资源，ID 为 RT_MANIFEST。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="d0ee2-112">使用 NULL 的参数调用时，将清除任何以前的读取清单。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="d0ee2-113">这样一来，就可以将链接器的状态重置为初始化时的状态。</span><span class="sxs-lookup"><span data-stu-id="d0ee2-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ee2-114">要求</span><span class="sxs-lookup"><span data-stu-id="d0ee2-114">Requirements</span></span>  
 <span data-ttu-id="d0ee2-115">需要 aLink</span><span class="sxs-lookup"><span data-stu-id="d0ee2-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ee2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ee2-116">See also</span></span>

- [<span data-ttu-id="d0ee2-117">IALink3 接口</span><span class="sxs-lookup"><span data-stu-id="d0ee2-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="d0ee2-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="d0ee2-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="d0ee2-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="d0ee2-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d0ee2-120">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="d0ee2-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
