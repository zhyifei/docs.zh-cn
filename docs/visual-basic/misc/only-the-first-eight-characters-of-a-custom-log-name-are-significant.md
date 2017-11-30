---
title: "在自定义日志名称中，只有前八个字符是有意义的"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: db2a0252-9ddd-4e93-a239-6a690cc09557
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 323fbacb9d269de778fb1f624d225551283a44a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="only-the-first-eight-characters-of-a-custom-log-name-are-significant"></a><span data-ttu-id="cf454-102">在自定义日志名称中，只有前八个字符是有意义的</span><span class="sxs-lookup"><span data-stu-id="cf454-102">Only the first eight characters of a custom log name are significant</span></span>
<span data-ttu-id="cf454-103">在检查事件日志名称的唯一性时，仅考虑前八个字符。</span><span class="sxs-lookup"><span data-stu-id="cf454-103">When checking event log names for uniqueness, only the first eight characters are considered.</span></span> <span data-ttu-id="cf454-104">当事件日志共享前八个字符时，则可能会导致冲突。</span><span class="sxs-lookup"><span data-stu-id="cf454-104">A conflict may result from event logs that share their first eight characters.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf454-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cf454-105">To correct this error</span></span>  
  
-   <span data-ttu-id="cf454-106">为事件日志命名，其中前八个字符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cf454-106">Give the event log a name in which the first eight characters are unique.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf454-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf454-107">See Also</span></span>  
 [<span data-ttu-id="cf454-108">如何： 创建和删除自定义事件日志</span><span class="sxs-lookup"><span data-stu-id="cf454-108">How to: Create and Remove Custom Event Logs</span></span>](http://msdn.microsoft.com/en-us/af9b7da0-80c7-46ac-b7f7-897063ddd503)  
 [<span data-ttu-id="cf454-109">管理事件日志</span><span class="sxs-lookup"><span data-stu-id="cf454-109">Administering Event Logs</span></span>](http://msdn.microsoft.com/en-us/35f53238-bdd2-417b-acd8-2fd9f7397f18)
