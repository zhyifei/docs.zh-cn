---
title: "为事件日志指定了无效名称"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fc5a2e93541063a129efaa0ce08fc19a98372126
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="7ba2b-102">为事件日志指定了无效名称</span><span class="sxs-lookup"><span data-stu-id="7ba2b-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="7ba2b-103">为事件日志指定了无效名称。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="7ba2b-104">通常名称中存在无效字符、文件名太长或空白文件名会导致此结果。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ba2b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7ba2b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="7ba2b-106">如果指定的名称多于 8 个字符，请确保与其他事件日志名称之间不存在冲突。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="7ba2b-107">当确定名称是否唯一时，将仅计算前八个字符。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="7ba2b-108">如果提供路径，请确保它被正确解析。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="7ba2b-109">检查此名称中是否不存在任何无效字符。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="7ba2b-110">不能在文件名中使用的字符包括 `<`、 `>`、 `:`、 `"`、 `/`、 `\`和 `|`。</span><span class="sxs-lookup"><span data-stu-id="7ba2b-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba2b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ba2b-111">See Also</span></span>  
 [<span data-ttu-id="7ba2b-112">如何：分析文件路径</span><span class="sxs-lookup"><span data-stu-id="7ba2b-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="7ba2b-113">如何：重命名文件</span><span class="sxs-lookup"><span data-stu-id="7ba2b-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [<span data-ttu-id="7ba2b-114">如何： 创建和删除自定义事件日志</span><span class="sxs-lookup"><span data-stu-id="7ba2b-114">How to: Create and Remove Custom Event Logs</span></span>](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)
