---
title: GetALinkMessageDll 函数
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449344"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="787da-102">GetALinkMessageDll 函数</span><span class="sxs-lookup"><span data-stu-id="787da-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="787da-103">查找并加载消息 DLL。</span><span class="sxs-lookup"><span data-stu-id="787da-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="787da-104">如果找不到或无法加载消息 DLL，则返回0。</span><span class="sxs-lookup"><span data-stu-id="787da-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="787da-105">消息 DLL 应位于其名称为语言 ID 的子目录中，或位于当前目录中。</span><span class="sxs-lookup"><span data-stu-id="787da-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787da-106">语法</span><span class="sxs-lookup"><span data-stu-id="787da-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="787da-107">要求</span><span class="sxs-lookup"><span data-stu-id="787da-107">Requirements</span></span>  
 <span data-ttu-id="787da-108">**标头：** alink。h</span><span class="sxs-lookup"><span data-stu-id="787da-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="787da-109">**库**： alink</span><span class="sxs-lookup"><span data-stu-id="787da-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787da-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="787da-110">See also</span></span>

- [<span data-ttu-id="787da-111">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="787da-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
