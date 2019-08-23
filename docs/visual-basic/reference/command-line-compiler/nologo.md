---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964380"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="a6c88-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6c88-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="a6c88-103">在编译期间取消显示版权标志和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a6c88-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c88-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6c88-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6c88-105">备注</span><span class="sxs-lookup"><span data-stu-id="a6c88-105">Remarks</span></span>  
 <span data-ttu-id="a6c88-106">如果指定`-nologo`, 则编译器不显示版权横幅。</span><span class="sxs-lookup"><span data-stu-id="a6c88-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="a6c88-107">默认情况，`-nologo` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="a6c88-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6c88-108">此`-nologo`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="a6c88-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c88-109">示例</span><span class="sxs-lookup"><span data-stu-id="a6c88-109">Example</span></span>  
 <span data-ttu-id="a6c88-110">以下代码将进行`T2.vb`编译, 并且不显示版权横幅。</span><span class="sxs-lookup"><span data-stu-id="a6c88-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6c88-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c88-111">See also</span></span>

- [<span data-ttu-id="a6c88-112">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="a6c88-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a6c88-113">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="a6c88-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
