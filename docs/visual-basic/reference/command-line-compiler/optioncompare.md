---
title: "/optioncompare |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
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
ms.openlocfilehash: c9512427cda0b6a3bcb0c1fe338b47ff9f779d19
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="optioncompare"></a><span data-ttu-id="67e93-102">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="67e93-102">/optioncompare</span></span>
<span data-ttu-id="67e93-103">指定如何进行字符串比较。</span><span class="sxs-lookup"><span data-stu-id="67e93-103">Specifies how string comparisons are made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e93-104">语法</span><span class="sxs-lookup"><span data-stu-id="67e93-104">Syntax</span></span>  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a><span data-ttu-id="67e93-105">备注</span><span class="sxs-lookup"><span data-stu-id="67e93-105">Remarks</span></span>  
 <span data-ttu-id="67e93-106">您可以指定`/optioncompare`在两种形式之一︰`/optioncompare:binary`使用二进制字符串比较和`/optioncompare:text`使用文本字符串比较。</span><span class="sxs-lookup"><span data-stu-id="67e93-106">You can specify `/optioncompare` in one of two forms: `/optioncompare:binary` to use binary string comparisons, and `/optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="67e93-107">默认情况下，编译器将使用`/optioncompare:binary`。</span><span class="sxs-lookup"><span data-stu-id="67e93-107">By default, the compiler uses `/optioncompare:binary`.</span></span>  
  
 <span data-ttu-id="67e93-108">在 Microsoft Windows 中，正在使用的代码页决定的二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="67e93-108">In Microsoft Windows, the code page being used determines the binary sort order.</span></span> <span data-ttu-id="67e93-109">以下是典型的二进制排序顺序︰</span><span class="sxs-lookup"><span data-stu-id="67e93-109">A typical binary sort order is as follows:</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="67e93-110">基于文本的字符串比较将基于由您的系统区域设置确定的不区分大小写的文本排序顺序。</span><span class="sxs-lookup"><span data-stu-id="67e93-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="67e93-111">典型的文本排序顺序如下所述︰</span><span class="sxs-lookup"><span data-stu-id="67e93-111">A typical text sort order is as follows:</span></span>  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="67e93-112">在 Visual Studio IDE 中设置 /optioncompare</span><span class="sxs-lookup"><span data-stu-id="67e93-112">To set /optioncompare in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="67e93-113">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="67e93-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="67e93-114">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="67e93-114">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="67e93-115">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="67e93-115">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="67e93-116">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="67e93-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="67e93-117">在修改此值**Option Compare**框。</span><span class="sxs-lookup"><span data-stu-id="67e93-117">Modify the value in the **Option Compare** box.</span></span>  
  
### <a name="to-set-optioncompare-programmatically"></a><span data-ttu-id="67e93-118">以编程方式设置 /optioncompare</span><span class="sxs-lookup"><span data-stu-id="67e93-118">To set /optioncompare programmatically</span></span>  
  
-   <span data-ttu-id="67e93-119">请参阅[Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="67e93-119">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e93-120">示例</span><span class="sxs-lookup"><span data-stu-id="67e93-120">Example</span></span>  
 <span data-ttu-id="67e93-121">下面的代码编译 P`rojFile.vb` ，并使用二进制字符串比较。</span><span class="sxs-lookup"><span data-stu-id="67e93-121">The following code compiles P`rojFile.vb` and uses binary string comparisons.</span></span>  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="67e93-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67e93-122">See Also</span></span>  
 <span data-ttu-id="67e93-123">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="67e93-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-124"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="67e93-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="67e93-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="67e93-127"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="67e93-128"> [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="67e93-128"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="67e93-129"> [“选项”对话框 ->“项目”->“Visual Basic 默认值”](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="67e93-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
