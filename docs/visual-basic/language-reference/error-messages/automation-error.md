---
title: 自动错误
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8a00efe988eb39be75818b5c2c401b58e5f7f2ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490877"
---
# <a name="automation-error"></a><span data-ttu-id="f0be1-102">自动错误</span><span class="sxs-lookup"><span data-stu-id="f0be1-102">Automation error</span></span>
<span data-ttu-id="f0be1-103">执行方法或者获取或设置对象变量的属性时发生错误。</span><span class="sxs-lookup"><span data-stu-id="f0be1-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="f0be1-104">错误由创建该对象的应用程序报告。</span><span class="sxs-lookup"><span data-stu-id="f0be1-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0be1-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f0be1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f0be1-106">检查 `Err` 对象的属性，以确定错误来源和错误性质。</span><span class="sxs-lookup"><span data-stu-id="f0be1-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="f0be1-107">在紧邻访问语句之前使用 `On Error Resume Next` 语句，然后检查紧邻访问语句之后是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="f0be1-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0be1-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0be1-108">See also</span></span>
- [<span data-ttu-id="f0be1-109">错误类型</span><span class="sxs-lookup"><span data-stu-id="f0be1-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="f0be1-110">与我们交流</span><span class="sxs-lookup"><span data-stu-id="f0be1-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
