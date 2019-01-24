---
title: 为事件日志指定了无效名称
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 242c5394011fd018a03f81b9b56bcfd7015682dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604388"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="88cee-102">为事件日志指定了无效名称</span><span class="sxs-lookup"><span data-stu-id="88cee-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="88cee-103">为事件日志指定了无效名称。</span><span class="sxs-lookup"><span data-stu-id="88cee-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="88cee-104">通常名称中存在无效字符、文件名太长或空白文件名会导致此结果。</span><span class="sxs-lookup"><span data-stu-id="88cee-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88cee-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="88cee-105">To correct this error</span></span>  
  
-   <span data-ttu-id="88cee-106">如果指定的名称多于 8 个字符，请确保与其他事件日志名称之间不存在冲突。</span><span class="sxs-lookup"><span data-stu-id="88cee-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="88cee-107">当确定名称是否唯一时，将仅计算前八个字符。</span><span class="sxs-lookup"><span data-stu-id="88cee-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="88cee-108">如果提供路径，请确保它被正确解析。</span><span class="sxs-lookup"><span data-stu-id="88cee-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="88cee-109">检查此名称中是否不存在任何无效字符。</span><span class="sxs-lookup"><span data-stu-id="88cee-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="88cee-110">不能在文件名中使用的字符包括 `<`、 `>`、 `:`、 `"`、 `/`、 `\`和 `|`。</span><span class="sxs-lookup"><span data-stu-id="88cee-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cee-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="88cee-111">See also</span></span>
- [<span data-ttu-id="88cee-112">如何：分析文件路径</span><span class="sxs-lookup"><span data-stu-id="88cee-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="88cee-113">如何：重命名文件</span><span class="sxs-lookup"><span data-stu-id="88cee-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)

