---
title: SetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 180eb1a3129cfcd96668ecfee11947c15c5e0915
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776912"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="3b358-102">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="3b358-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="3b358-103">分配程序集级别属性。</span><span class="sxs-lookup"><span data-stu-id="3b358-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b358-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b358-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b358-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b358-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3b358-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="3b358-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3b358-107">定义属性的文件。</span><span class="sxs-lookup"><span data-stu-id="3b358-107">File that defines the property.</span></span> <span data-ttu-id="3b358-108">如果不指示未`AssemblyID`绑定的 .netmodule，则可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3b358-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="3b358-109">指示要修改的选项。</span><span class="sxs-lookup"><span data-stu-id="3b358-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="3b358-110">选项的新值。</span><span class="sxs-lookup"><span data-stu-id="3b358-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b358-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3b358-111">Return Value</span></span>  
 <span data-ttu-id="3b358-112">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3b358-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b358-113">要求</span><span class="sxs-lookup"><span data-stu-id="3b358-113">Requirements</span></span>  
 <span data-ttu-id="3b358-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="3b358-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b358-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b358-115">See also</span></span>

- [<span data-ttu-id="3b358-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="3b358-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3b358-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="3b358-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3b358-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="3b358-118">ALink API</span></span>](index.md)
