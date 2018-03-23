---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e5eb9db7af861a8439b47adb8f5e515331fae6e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="c954e-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c954e-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="c954e-103">在编译期间取消显示版权标志和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="c954e-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c954e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c954e-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="c954e-105">备注</span><span class="sxs-lookup"><span data-stu-id="c954e-105">Remarks</span></span>  
 <span data-ttu-id="c954e-106">如果指定`-nologo`，编译器不会显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="c954e-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="c954e-107">默认情况，`-nologo` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="c954e-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c954e-108">`-nologo`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="c954e-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c954e-109">示例</span><span class="sxs-lookup"><span data-stu-id="c954e-109">Example</span></span>  
 <span data-ttu-id="c954e-110">下面的代码编译`T2.vb`并且不显示版权标志。</span><span class="sxs-lookup"><span data-stu-id="c954e-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c954e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c954e-111">See Also</span></span>  
 [<span data-ttu-id="c954e-112">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="c954e-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c954e-113">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="c954e-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
