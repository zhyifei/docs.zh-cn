---
title: 剪贴板格式无效
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: f2a0ab33c1749117d5de4987e85c44602ccd29ce
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245552"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="ab887-102">剪贴板格式无效</span><span class="sxs-lookup"><span data-stu-id="ab887-102">Clipboard format is not valid</span></span>
<span data-ttu-id="ab887-103">指定的剪贴板格式，与正在执行的方法不兼容。</span><span class="sxs-lookup"><span data-stu-id="ab887-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="ab887-104">此错误的可能原因是：</span><span class="sxs-lookup"><span data-stu-id="ab887-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="ab887-105">使用剪贴板`GetText`或`SetText`剪贴板格式以外的其他方法`vbCFText`或`vbCFLink`。</span><span class="sxs-lookup"><span data-stu-id="ab887-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="ab887-106">使用剪贴板`GetData`或`SetData`剪贴板格式以外的其他方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。</span><span class="sxs-lookup"><span data-stu-id="ab887-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="ab887-107">使用`GetData`或`SetData`方法的`DataObject`与已注册的格式 （HC000-& HFFFF），由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ab887-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ab887-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ab887-108">To correct this error</span></span>  
  
-   <span data-ttu-id="ab887-109">删除无效的格式，并指定一个有效。</span><span class="sxs-lookup"><span data-stu-id="ab887-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab887-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab887-110">See Also</span></span>  
 [<span data-ttu-id="ab887-111">剪贴板：添加其他格式</span><span class="sxs-lookup"><span data-stu-id="ab887-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
