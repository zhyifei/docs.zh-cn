---
title: -langversion （Visual Basic）
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 5f59f1c4c269a52131a324bbd2bfbe817ab794a4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197085"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="4c7dd-102">-langversion （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="4c7dd-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="4c7dd-103">导致编译器仅接受指定 Visual Basic 语言版本中包含的语法。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c7dd-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c7dd-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4c7dd-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="4c7dd-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-106">Required.</span></span> <span data-ttu-id="4c7dd-107">要在编译过程中使用的语言版本。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="4c7dd-108">接受的值为 `9`、`10`、`11`、`12`、`14`、`15`、`15.3`、`15.5`、`default` 和 `latest`。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="4c7dd-109">还可以使用 `.0` 作为次要版本来指定任何整数，例如 `11.0`。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="4c7dd-110">可以通过在命令行上指定 `-langversion:?`，查看所有可能值的列表。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c7dd-111">备注</span><span class="sxs-lookup"><span data-stu-id="4c7dd-111">Remarks</span></span>  
 <span data-ttu-id="4c7dd-112">`-langversion` 选项指定编译器接受的语法。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="4c7dd-113">例如，如果指定语言版本为9.0，则编译器将生成仅在版本10.0 和更高版本中有效的语法错误。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="4c7dd-114">当开发面向不同版本的 .NET Framework 的应用程序时，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="4c7dd-115">例如，如果以 .NET Framework 3.5 为目标，则可以使用此选项来确保不使用语言版本10.0 中的语法。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="4c7dd-116">只能使用命令行直接设置 `-langversion`。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="4c7dd-117">有关详细信息，请参阅[面向特定的 .NET Framework 版本](/visualstudio/ide/visual-studio-multi-targeting-overview)。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c7dd-118">示例</span><span class="sxs-lookup"><span data-stu-id="4c7dd-118">Example</span></span>  
 <span data-ttu-id="4c7dd-119">下面的代码编译 Visual Basic 9.0 `sample.vb`。</span><span class="sxs-lookup"><span data-stu-id="4c7dd-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c7dd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c7dd-120">See also</span></span>

- [<span data-ttu-id="4c7dd-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4c7dd-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4c7dd-122">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4c7dd-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="4c7dd-123">面向特定的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="4c7dd-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
