---
title: 没有可访问&#39;Main&#39;中找到具有适当签名方法&#39;&lt;名称&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593215"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="f7a08-102">没有可访问&#39;Main&#39;中找到具有适当签名方法&#39;&lt;名称&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="f7a08-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="f7a08-103">命令行应用程序必须具有`Sub Main`定义。</span><span class="sxs-lookup"><span data-stu-id="f7a08-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="f7a08-104">`Main` 必须声明为`Public Shared`如果它定义在类中，或作为`Public`如果的模块中定义。</span><span class="sxs-lookup"><span data-stu-id="f7a08-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="f7a08-105">**错误 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="f7a08-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7a08-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f7a08-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f7a08-107">定义`Public Sub Main`为你的项目的过程。</span><span class="sxs-lookup"><span data-stu-id="f7a08-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="f7a08-108">将其声明为`Shared`当且仅当定义的类中。</span><span class="sxs-lookup"><span data-stu-id="f7a08-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a08-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a08-109">See Also</span></span>  
 [<span data-ttu-id="f7a08-110">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="f7a08-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="f7a08-111">过程</span><span class="sxs-lookup"><span data-stu-id="f7a08-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
