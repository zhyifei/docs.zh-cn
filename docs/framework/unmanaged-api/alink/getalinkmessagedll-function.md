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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787483"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="55034-102">GetALinkMessageDll 函数</span><span class="sxs-lookup"><span data-stu-id="55034-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="55034-103">查找并加载消息 DLL。</span><span class="sxs-lookup"><span data-stu-id="55034-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="55034-104">如果找不到或无法加载消息 DLL，则返回0。</span><span class="sxs-lookup"><span data-stu-id="55034-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="55034-105">消息 DLL 应位于其名称为语言 ID 的子目录中，或位于当前目录中。</span><span class="sxs-lookup"><span data-stu-id="55034-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55034-106">语法</span><span class="sxs-lookup"><span data-stu-id="55034-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="55034-107">要求</span><span class="sxs-lookup"><span data-stu-id="55034-107">Requirements</span></span>  
 <span data-ttu-id="55034-108">**标头：** alink。h</span><span class="sxs-lookup"><span data-stu-id="55034-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="55034-109">**库**： alink</span><span class="sxs-lookup"><span data-stu-id="55034-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55034-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="55034-110">See also</span></span>

- [<span data-ttu-id="55034-111">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="55034-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
