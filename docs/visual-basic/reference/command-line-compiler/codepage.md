---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 8aee51df3ba9f92ca662fbbfbd73998e4a3b4538
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43882599"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="3f0b2-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f0b2-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="3f0b2-103">指定要用于编译中所有源代码文件的代码页。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f0b2-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f0b2-105">自变量</span><span class="sxs-lookup"><span data-stu-id="3f0b2-105">Arguments</span></span>  
  
|<span data-ttu-id="3f0b2-106">术语</span><span class="sxs-lookup"><span data-stu-id="3f0b2-106">Term</span></span>|<span data-ttu-id="3f0b2-107">定义</span><span class="sxs-lookup"><span data-stu-id="3f0b2-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="3f0b2-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-108">Required.</span></span> <span data-ttu-id="3f0b2-109">编译器使用指定的代码页`id`解释源代码文件的编码。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f0b2-110">备注</span><span class="sxs-lookup"><span data-stu-id="3f0b2-110">Remarks</span></span>  
 <span data-ttu-id="3f0b2-111">若要编译源代码保存使用特定的编码，可以使用`-codepage`以指定应使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="3f0b2-112">`-codepage`选项适用于编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="3f0b2-113">有关详细信息，请参阅[.NET Framework 中的字符编码](https://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-113">For more information, see [Character Encoding in the .NET Framework](https://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="3f0b2-114">`-codepage`如果源代码文件已保存签名中使用当前 ANSI 代码页、 Unicode 或 utf-8，则不需要选项。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="3f0b2-115">Visual Studio 将保存所有源代码文件的当前 ANSI 代码页与默认情况下，除非用户指定在另一种编码**编码**对话框。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="3f0b2-116">Visual Studio 将使用**编码**对话框以打开用不同的代码页保存的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f0b2-117">`-codepage`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="3f0b2-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0b2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0b2-118">See Also</span></span>  
 [<span data-ttu-id="3f0b2-119">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="3f0b2-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
