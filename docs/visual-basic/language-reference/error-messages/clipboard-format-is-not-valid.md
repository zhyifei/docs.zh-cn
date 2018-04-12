---
title: 剪贴板格式无效
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="341e8-102">剪贴板格式无效</span><span class="sxs-lookup"><span data-stu-id="341e8-102">Clipboard format is not valid</span></span>
<span data-ttu-id="341e8-103">指定的剪贴板格式是与正在执行的方法不兼容。</span><span class="sxs-lookup"><span data-stu-id="341e8-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="341e8-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="341e8-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="341e8-105">使用剪贴板的`GetText`或`SetText`以外的其他剪贴板格式的方法`vbCFText`或`vbCFLink`。</span><span class="sxs-lookup"><span data-stu-id="341e8-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="341e8-106">使用剪贴板的`GetData`或`SetData`以外的其他剪贴板格式的方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。</span><span class="sxs-lookup"><span data-stu-id="341e8-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="341e8-107">使用`DataObject``GetData`方法或`SetData`方法替换为已注册格式 (HC000-& HFFFF)，由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows 一起。</span><span class="sxs-lookup"><span data-stu-id="341e8-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="341e8-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="341e8-108">To correct this error</span></span>  
  
-   <span data-ttu-id="341e8-109">删除无效的格式，并指定一个有效。</span><span class="sxs-lookup"><span data-stu-id="341e8-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341e8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="341e8-110">See Also</span></span>  
 [<span data-ttu-id="341e8-111">剪贴板：添加其他格式</span><span class="sxs-lookup"><span data-stu-id="341e8-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
