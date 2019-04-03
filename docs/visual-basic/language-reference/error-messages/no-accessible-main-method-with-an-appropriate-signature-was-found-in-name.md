---
title: 在“<name>”中找不到任何具有合适签名的可访问“Main”方法
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818353"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="1d63e-102">任何具有合适签名的可访问 Main 方法中找到\<名称 ></span><span class="sxs-lookup"><span data-stu-id="1d63e-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="1d63e-103">命令行应用程序必须具有`Sub Main`定义。</span><span class="sxs-lookup"><span data-stu-id="1d63e-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="1d63e-104">`Main` 必须声明为`Public Shared`如果它定义在类中，或作为`Public`如果模块中定义。</span><span class="sxs-lookup"><span data-stu-id="1d63e-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="1d63e-105">**错误 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="1d63e-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d63e-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1d63e-106">To correct this error</span></span>  
  
-   <span data-ttu-id="1d63e-107">定义`Public Sub Main`为你的项目的过程。</span><span class="sxs-lookup"><span data-stu-id="1d63e-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="1d63e-108">将其声明为`Shared`当且仅当在类定义。</span><span class="sxs-lookup"><span data-stu-id="1d63e-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d63e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d63e-109">See also</span></span>

- [<span data-ttu-id="1d63e-110">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="1d63e-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="1d63e-111">过程</span><span class="sxs-lookup"><span data-stu-id="1d63e-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
