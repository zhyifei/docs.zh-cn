---
title: "自动化错误 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
dev_langs:
- VB
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b48ada07663889db633a43fabb577d5129c5cbb3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="automation-error"></a><span data-ttu-id="f2ed1-102">自动错误</span><span class="sxs-lookup"><span data-stu-id="f2ed1-102">Automation error</span></span>
<span data-ttu-id="f2ed1-103">执行方法或者获取或设置对象变量的属性时发生错误。</span><span class="sxs-lookup"><span data-stu-id="f2ed1-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="f2ed1-104">错误由创建该对象的应用程序报告。</span><span class="sxs-lookup"><span data-stu-id="f2ed1-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2ed1-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f2ed1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2ed1-106">检查 `Err` 对象的属性，以确定错误来源和错误性质。</span><span class="sxs-lookup"><span data-stu-id="f2ed1-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="f2ed1-107">在紧邻访问语句之前使用 `On Error Resume Next` 语句，然后检查紧邻访问语句之后是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="f2ed1-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ed1-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ed1-108">See Also</span></span>  
 <span data-ttu-id="f2ed1-109">[错误类型](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="f2ed1-109">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="f2ed1-110"> [与我们交流](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="f2ed1-110"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
