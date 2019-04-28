---
title: 不支持 Set 语句(只读属性)
ms.date: 07/20/2015
f1_keywords:
- vbrID383
ms.assetid: 0b97b683-6626-42ec-af0b-aaa3c973a76b
ms.openlocfilehash: d3dd928f65bc4939e6e204d71a3a5544a30a4293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61594849"
---
# <a name="set-not-supported-read-only-property"></a><span data-ttu-id="2d3b2-102">不支持 Set 语句(只读属性)</span><span class="sxs-lookup"><span data-stu-id="2d3b2-102">Set not supported (read-only property)</span></span>
<span data-ttu-id="2d3b2-103">试图设置或更改只读属性。</span><span class="sxs-lookup"><span data-stu-id="2d3b2-103">You tried to set or change a property that is read only.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d3b2-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2d3b2-104">To correct this error</span></span>  
  
1. <span data-ttu-id="2d3b2-105">从代码中删除对该属性的引用。</span><span class="sxs-lookup"><span data-stu-id="2d3b2-105">Remove the reference to the property from your code.</span></span>  
  
2. <span data-ttu-id="2d3b2-106">更改引用以便在运行时仅返回该属性的值。</span><span class="sxs-lookup"><span data-stu-id="2d3b2-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3b2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d3b2-107">See also</span></span>

- [<span data-ttu-id="2d3b2-108">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="2d3b2-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
