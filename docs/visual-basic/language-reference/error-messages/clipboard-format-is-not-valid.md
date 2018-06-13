---
title: 剪贴板格式无效
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586216"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="1842b-102">剪贴板格式无效</span><span class="sxs-lookup"><span data-stu-id="1842b-102">Clipboard format is not valid</span></span>
<span data-ttu-id="1842b-103">指定的剪贴板格式是与正在执行的方法不兼容。</span><span class="sxs-lookup"><span data-stu-id="1842b-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="1842b-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="1842b-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="1842b-105">使用剪贴板的`GetText`或`SetText`以外的其他剪贴板格式的方法`vbCFText`或`vbCFLink`。</span><span class="sxs-lookup"><span data-stu-id="1842b-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="1842b-106">使用剪贴板的`GetData`或`SetData`以外的其他剪贴板格式的方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。</span><span class="sxs-lookup"><span data-stu-id="1842b-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="1842b-107">使用`DataObject``GetData`方法或`SetData`方法替换为已注册格式 (HC000-& HFFFF)，由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows 一起。</span><span class="sxs-lookup"><span data-stu-id="1842b-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1842b-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1842b-108">To correct this error</span></span>  
  
-   <span data-ttu-id="1842b-109">删除无效的格式，并指定一个有效。</span><span class="sxs-lookup"><span data-stu-id="1842b-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1842b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1842b-110">See Also</span></span>  
 [<span data-ttu-id="1842b-111">剪贴板：添加其他格式</span><span class="sxs-lookup"><span data-stu-id="1842b-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
