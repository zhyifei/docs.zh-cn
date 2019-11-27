---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: a38fb4be9347b3372b4a459fce2e96b9e38c3a51
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343542"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="9c746-102">-代码页（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="9c746-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="9c746-103">指定要用于编译中所有源代码文件的代码页。</span><span class="sxs-lookup"><span data-stu-id="9c746-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c746-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c746-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c746-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c746-105">Arguments</span></span>  
  
|<span data-ttu-id="9c746-106">术语</span><span class="sxs-lookup"><span data-stu-id="9c746-106">Term</span></span>|<span data-ttu-id="9c746-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9c746-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="9c746-108">必需。</span><span class="sxs-lookup"><span data-stu-id="9c746-108">Required.</span></span> <span data-ttu-id="9c746-109">编译器使用 `id` 指定的代码页来解释源文件的编码。</span><span class="sxs-lookup"><span data-stu-id="9c746-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c746-110">备注</span><span class="sxs-lookup"><span data-stu-id="9c746-110">Remarks</span></span>  
 <span data-ttu-id="9c746-111">若要编译使用特定编码保存的源代码，可以使用 `-codepage` 指定应使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="9c746-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="9c746-112">`-codepage` 选项适用于编译中的所有源代码文件。</span><span class="sxs-lookup"><span data-stu-id="9c746-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="9c746-113">有关详细信息，请参阅[.NET Framework 中的字符编码](../../../standard/base-types/character-encoding.md)。</span><span class="sxs-lookup"><span data-stu-id="9c746-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="9c746-114">如果源代码文件是使用当前 ANSI 代码页、Unicode 或 UTF-8 （带有签名）保存的，则不需要 `-codepage` 选项。</span><span class="sxs-lookup"><span data-stu-id="9c746-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="9c746-115">默认情况下，Visual Studio 会将所有源代码文件连同当前 ANSI 代码页一起保存，除非用户在**编码**对话框中指定了另一编码。</span><span class="sxs-lookup"><span data-stu-id="9c746-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="9c746-116">Visual Studio 使用 "**编码**" 对话框打开使用其他代码页保存的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="9c746-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c746-117">`-codepage` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="9c746-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c746-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c746-118">See also</span></span>

- [<span data-ttu-id="9c746-119">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="9c746-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
