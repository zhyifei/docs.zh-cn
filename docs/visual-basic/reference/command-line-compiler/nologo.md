---
title: "/nologo (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners, suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
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
ms.openlocfilehash: fe03c36f46717248269c9aaec13b40569161b0e0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nologo-visual-basic"></a><span data-ttu-id="dc1d7-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc1d7-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="dc1d7-103">在编译期间取消显示版权标志和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="dc1d7-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc1d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc1d7-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="dc1d7-105">备注</span><span class="sxs-lookup"><span data-stu-id="dc1d7-105">Remarks</span></span>  
 <span data-ttu-id="dc1d7-106">如果指定`/nologo`，编译器将不显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="dc1d7-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="dc1d7-107">默认情况，`/nologo` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="dc1d7-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc1d7-108">`/nologo`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="dc1d7-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc1d7-109">示例</span><span class="sxs-lookup"><span data-stu-id="dc1d7-109">Example</span></span>  
 <span data-ttu-id="dc1d7-110">下面的代码编译`T2.vb`并且不显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="dc1d7-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc1d7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc1d7-111">See Also</span></span>  
 <span data-ttu-id="dc1d7-112">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc1d7-112">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="dc1d7-113"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="dc1d7-113"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
