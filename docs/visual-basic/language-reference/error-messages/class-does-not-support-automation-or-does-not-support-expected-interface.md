---
title: 类不支持自动化或不支持所需的接口
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: d5b47b39742a995be6076ddc0edc17f1ec94dade
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534157"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a><span data-ttu-id="14f12-102">类不支持自动化或不支持所需的接口</span><span class="sxs-lookup"><span data-stu-id="14f12-102">Class does not support Automation or does not support expected interface</span></span>
<span data-ttu-id="14f12-103">在 `GetObject` 或 `CreateObject` 函数调用中所指定的类尚未公开可编程接口，或者将项目从 .dll 更改为 .exe 或相反。</span><span class="sxs-lookup"><span data-stu-id="14f12-103">Either the class you specified in the `GetObject` or `CreateObject` function call has not exposed a programmability interface, or you changed a project from .dll to .exe, or vice versa.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14f12-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="14f12-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="14f12-105">检查创建对象的应用程序的相关文档，确定该对象类是否存在使用自动化的限制。</span><span class="sxs-lookup"><span data-stu-id="14f12-105">Check the documentation of the application that created the object for limitations on the use of automation with this class of object.</span></span>  
  
2.  <span data-ttu-id="14f12-106">如果将项目从 .dll 更改为 .exe 或者相反，必须手动注销旧的 .dll 或 .exe。</span><span class="sxs-lookup"><span data-stu-id="14f12-106">If you changed a project from .dll to .exe or vice versa, you must manually unregister the old .dll or .exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f12-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="14f12-107">See also</span></span>
- [<span data-ttu-id="14f12-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="14f12-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="14f12-109">与我们交流</span><span class="sxs-lookup"><span data-stu-id="14f12-109">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
