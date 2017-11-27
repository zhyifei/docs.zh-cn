---
title: "自动错误"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a><span data-ttu-id="ae42b-102">自动错误</span><span class="sxs-lookup"><span data-stu-id="ae42b-102">Automation error</span></span>
<span data-ttu-id="ae42b-103">执行方法或者获取或设置对象变量的属性时发生错误。</span><span class="sxs-lookup"><span data-stu-id="ae42b-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="ae42b-104">错误由创建该对象的应用程序报告。</span><span class="sxs-lookup"><span data-stu-id="ae42b-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae42b-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ae42b-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="ae42b-106">检查 `Err` 对象的属性，以确定错误来源和错误性质。</span><span class="sxs-lookup"><span data-stu-id="ae42b-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="ae42b-107">在紧邻访问语句之前使用 `On Error Resume Next` 语句，然后检查紧邻访问语句之后是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="ae42b-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae42b-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae42b-108">See Also</span></span>  
 [<span data-ttu-id="ae42b-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="ae42b-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="ae42b-110">与我们交流</span><span class="sxs-lookup"><span data-stu-id="ae42b-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
