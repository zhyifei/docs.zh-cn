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
ms.openlocfilehash: 825bb945e0d8662a4dadc9d688de6a677165df4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741481"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="886ca-102">SetManifestFile 方法</span><span class="sxs-lookup"><span data-stu-id="886ca-102">SetManifestFile Method</span></span>
<span data-ttu-id="886ca-103">可以指定或重置链接器在创建程序集时使用的清单文件。</span><span class="sxs-lookup"><span data-stu-id="886ca-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="886ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="886ca-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="886ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="886ca-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="886ca-106">Win32 资源的 blob 的内容放入清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="886ca-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="886ca-107">返回值</span><span class="sxs-lookup"><span data-stu-id="886ca-107">Return Value</span></span>  
 <span data-ttu-id="886ca-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="886ca-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="886ca-109">备注</span><span class="sxs-lookup"><span data-stu-id="886ca-109">Remarks</span></span>  
 <span data-ttu-id="886ca-110">询问 Win32ResBlob 前调用此操作。</span><span class="sxs-lookup"><span data-stu-id="886ca-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="886ca-111">值`pszFile`参数是其内容读取，并将其置于具有 ID 的 RT_MANIFEST Win32 资源的清单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="886ca-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="886ca-112">通过使用 NULL 的参数调用时，将清除任何以前读取的清单。</span><span class="sxs-lookup"><span data-stu-id="886ca-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="886ca-113">这样，一个用于将链接器的状态重置为初始化时。</span><span class="sxs-lookup"><span data-stu-id="886ca-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="886ca-114">要求</span><span class="sxs-lookup"><span data-stu-id="886ca-114">Requirements</span></span>  
 <span data-ttu-id="886ca-115">需要 aLink.h</span><span class="sxs-lookup"><span data-stu-id="886ca-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="886ca-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="886ca-116">See also</span></span>

- [<span data-ttu-id="886ca-117">IALink3 接口</span><span class="sxs-lookup"><span data-stu-id="886ca-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="886ca-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="886ca-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="886ca-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="886ca-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="886ca-120">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="886ca-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
