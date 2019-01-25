---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 6fffe264377474bba14f6f086b521ccf9bd04adf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534454"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="eac95-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eac95-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="eac95-103">使编译器接受仅包含指定版本的 Visual Basic 语言的语法。</span><span class="sxs-lookup"><span data-stu-id="eac95-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac95-104">语法</span><span class="sxs-lookup"><span data-stu-id="eac95-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="eac95-105">自变量</span><span class="sxs-lookup"><span data-stu-id="eac95-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="eac95-106">必需。</span><span class="sxs-lookup"><span data-stu-id="eac95-106">Required.</span></span> <span data-ttu-id="eac95-107">要在编译期间使用的语言版本。</span><span class="sxs-lookup"><span data-stu-id="eac95-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="eac95-108">接受的值是`9`， `10`， `11`， `12`， `14`， `15`， `15.3`， `15.5`，`default`和`latest`。</span><span class="sxs-lookup"><span data-stu-id="eac95-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="eac95-109">任何整数还可以指定使用`.0`次要版本，例如，作为`11.0`。</span><span class="sxs-lookup"><span data-stu-id="eac95-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="eac95-110">您可以看到所有可能值的列表，通过指定`-langversion:?`命令行上。</span><span class="sxs-lookup"><span data-stu-id="eac95-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eac95-111">备注</span><span class="sxs-lookup"><span data-stu-id="eac95-111">Remarks</span></span>  
 <span data-ttu-id="eac95-112">`-langversion`选项指定编译器接受何种语法。</span><span class="sxs-lookup"><span data-stu-id="eac95-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="eac95-113">例如，如果你指定的语言版本为 9.0，编译器将生成有效仅在版本 10.0 及更高版本的语法的错误。</span><span class="sxs-lookup"><span data-stu-id="eac95-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="eac95-114">开发面向不同版本的.NET Framework 的应用程序时，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="eac95-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="eac95-115">例如，如果面向.NET Framework 3.5，可以使用此选项以确保不使用从语言版本 10.0 的语法。</span><span class="sxs-lookup"><span data-stu-id="eac95-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="eac95-116">可以设置`-langversion`直接只能通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="eac95-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="eac95-117">有关详细信息，请参阅[面向特定的 .NET Framework 版本](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)。</span><span class="sxs-lookup"><span data-stu-id="eac95-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eac95-118">示例</span><span class="sxs-lookup"><span data-stu-id="eac95-118">Example</span></span>  
 <span data-ttu-id="eac95-119">下面的代码编译`sample.vb`为 Visual Basic 9.0。</span><span class="sxs-lookup"><span data-stu-id="eac95-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="eac95-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="eac95-120">See also</span></span>
- [<span data-ttu-id="eac95-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="eac95-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="eac95-122">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="eac95-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="eac95-123">面向特定的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="eac95-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
