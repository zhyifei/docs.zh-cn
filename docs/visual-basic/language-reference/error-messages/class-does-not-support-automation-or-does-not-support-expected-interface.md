---
title: 类不支持自动化或不支持所需的接口
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6528ceabeb7fb7a1cdc0beff2fd362632a0a0c9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="189d4-102">类不支持自动化或不支持所需的接口</span><span class="sxs-lookup"><span data-stu-id="189d4-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="189d4-103">在 `GetObject` 或 `CreateObject` 函数调用中所指定的类尚未公开可编程接口，或者将项目从 .dll 更改为 .exe 或相反。</span><span class="sxs-lookup"><span data-stu-id="189d4-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="189d4-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="189d4-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="189d4-105">检查创建对象的应用程序的相关文档，确定该对象类是否存在使用自动化的限制。</span><span class="sxs-lookup"><span data-stu-id="189d4-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="189d4-106">如果将项目从 .dll 更改为 .exe 或者相反，必须手动注销旧的 .dll 或 .exe。</span><span class="sxs-lookup"><span data-stu-id="189d4-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189d4-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="189d4-107">See Also</span></span>  
 [<span data-ttu-id="189d4-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="189d4-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="189d4-109">与我们交流</span><span class="sxs-lookup"><span data-stu-id="189d4-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
